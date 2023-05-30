# Building Microservices

by Sam Newman

## 8. Deployment

### Principles of Microservice Deployment

#### Isolated execution

- Microservices don't share computing resources.
- Microservices can not impact other instances running nearby.

#### Focus on automation

- Automate everything.

#### Infrastructure as Code

- Store infrastructure configuration in source control.
- Use right tools: Terraform, Pulumi, Puppet, Chef, Ansible.

#### Zero-Downtime Deployment

- Deploy new version of a microservice without any downtime to users or other dependent systems.

#### Desired state management

- Use a platform that maintains your microservices in a defined state (number of instances, allocated resources).

### Deployment Options

#### Physical machine

* A microservice instance is deployed on a physical machine, with no virtualization.
* If several microservices are deployed on the same machine, **this violates the principle of isolated execution**.
* Use Puppet or Chef to automate configuration of physical machines.

#### Virtual machine

* A microservice instance is deployed on a virtual machine like AWS EC2 instance.
* Requires hypervisor that takes away CPU/ IO and memory of the physical machine to:
    * to map resources like CPU and memory from the virtual host to the physical host;
    * to act as a control layer, allowing us to manipulate the virtual machine themselves.
* VMs do very well in terms of isolation, but at a cost incurred by resource allocation, configuration and automation
  complexity.
* Many organizations used VMs for running large-scale microservice systems (e.g. Netflix on AWS EC2).

#### Container

* A microservice instance runs as a separate container on a virtual or physical machine.
  That container runtime may be changed by a container orchestration tool like Kubernetes.
* Key technologies: Docker, LXC, Kubernetes.
* Give due thought to the security of the code written by other in terms of bypassing container-level isolation.

#### Application container

* A microservice instance is run inside an application container that manages other application instances, typically on
  the same runtime.
* For example, .NET applications behind IIS or Java applications into something Weblogic or Tomcat.
* Rarely (or almost not)  adopted for microservices due to the weak isolation guarantees and scalability problems.

#### Platform as a Service (PaaS)

* A more highly abstracted platform is used to deploy microservice instances, often abstracting away all concepts of the
  underlying servers used to run your microservices.
* Examples include Heroku, Google App Engine, and AWS Beanstalk.

#### Function as a Service (Faas), Serverless

* A microservice instance is deployed as a function, which is executed on demand.
* Examples are AWS Lambda, Azure Functions.
* Arguably, FaaS is not a deployment option for microservices, but rather a way of implementing microservices.
* Limitations are:
    * Lack of control over the execution environment;
    * Limited execution time (e.g. 15 minute soft limit on AWS Lambda);
    * Function invocations are considered to be stateless.
* Mapping to microservices:
    * Function per microservice
    * Function per aggregate

### Which Deployment Option to Choose?

1. If it ain't broke, don't fix it.
2. Give up as much control as you can, then give away just a bit more. If you can use a PaaS, do so.
3. Containers are not pain free, but they are a good compromise between control and ease of use. Expect Kubernetes in
   your future.

### Kubernetes and Container Orchestration

* (!) Kubernetes is not a deployment platform, but rather a container orchestration tool.
* Platform is what goes on top of Kubernetes: Operators, Istio, Knative, etc.
* If you need a general purpose scheduler, take a look at Mesos or Nomad.

### Progressive Delivery

* Separate the concept of deployment from the concept of release.
* **Deployment** is installing some version of your software into an environment.
* **Release** is making that version of the software available to users.

#### Feature Flags

#### Canary Releases

#### Parallel Runs

* Run different implementations of the same microservice side by side, send requests to both and then compare the
  results.

## 11. Security

:exclamation: (If you are not security expert) Aim simply to be **conscious incompetent**: understand what you don't
know and be aware of your limits.

:exclamation: Remember about the back door while securing the front one.

:exclamation: Use holistic approach.

:exclamation: The cose of any security implementation should be justified (and driven) by your _threat model_.

### Core Principles of Cybersecurity

* **The Least Privilege**: A user or application should only have the minimum set of privileges required to do their
  job.
* **Defense in Depth**: Don't rely on a single security mechanism to protect your system. Build multiple layers of
  security, so that if one fails, another will be there to protect you.
* **Automation**: Automate everything.
* **DevSecOps**: Security should be part of the delivery process, not an afterthought.

### Functions of Cybersecurity

:exclamation: Build your **treat model**.

* **Identify**: the assets you need to protect, the threats to those assets, your potential attackers.
* **Protect**: your assets from the threats you have identified.
* **Detect**: when an attack is happening. Use external tools like AquaSec (https://www.aquasec.com/).
* **Respond**: to an attack. Look after users in the event of an attack. Focus on openness and safety. Learn the lessons
  and ensure that similar incidents are less likely to happen.
* **Recover**: from an attack.

### Foundations of Application Security

* **Credentials**. Things to consider: creation, distribution, storage, monitoring, rotation, revocation, limiting the
  scope.
* **Patching**: Monitor vulnerabilities in your dependencies and patch them as soon as possible. Use platforms that
  automatically patch your dependencies (AWS ECS vs AWS EC2).
* **Backups**. Data is valuable, so back it up. Target backups to the state that is most valuable. Keep backups separate
  from your main production environment. Make sure the backups actually work by restoring them.
* **Rebuild**. Make sure you can rebuild your system from scratch with a minimum of fuss.

### Implicit Trust vs Zero Trust

* **Implicit Trust**. All trusted inside the system's perimeter.
* **Zero Trust**. Be paranoid. Assume that every request is like coming from anyone from public Internet. Zero trust,
  fundamentally, is a mindset. Zero trust is a spectrum, not a binary state.
* **Zoned Approach**. Split your system into zones, and apply different levels of trust to each zone.

### Securing Data

* **Data in Transit**. Things to consider: server identity, client identity, visibility of data, manipulation of data.
* **Data at Rest**. Things to consider: encryption, key management, access control, backups, data retention. Go with the
  well-known specifications and libraries implementing them. Pick your targets for encryption. Be **frugal**: keep only
  mission-critical data only. If you don't store it, no one can steal it and no one can ask for
  it either.

### Authentication and Authorization

* **Authentication** is the process by which we confirm that a party is who they say they are.
* **Authorization** is the process by which we confirm that a party is allowed to do what they are trying to do.
* **Server-to-Server Authentication**. API Keys. Mutual TLS (mTLS).
* **Human Authentication**. Passwords, MFA, SSO.
* **Single Sign-On Gateway**. A gateway acts as a proxy, sitting between your services and the outside world. Favour **
  coarse-grained authorization** over fine-grained authorization: leave further authorization decisions on the
  downstream microservices.
* **Confused Deputy Problem**. It occurs when an upstream party tricks an intermediate party into doing things it
  shouldn't be doing. For example, when a customer asking for orders that are not theirs guessing order IDs.
* Favour **decentralized authorization** over centralized one. Each microservice is responsible for its own
  authorization. Issue JWT with request principal information on SSO gateway and pass it down to the microservices.
  Separate user JWTs used for logging in from service JWTs used for authorization.
* **JWT Web Tokens**. Challenges to consider: public key accessibility, long-lived tokens (at what point is having a
  longer-lived token more problematic than having no token?), token size (prefer other mechanism when token size becomes
  a problem).

## 12. Resiliency

:exclamation: We cannot achieve resiliency just thinking about our software and infrastructure; we also have to think
about our people, processes, and organizations.
:exclamation: Failure is everywhere.

Four main concepts:

* **Robustness**: the ability to absort expected perturbations.
* **Rebound**: the ability to recover after a traumatic event.
* **Graceful extensibility**: the ability to deal with a situation that is unexpected. Have right people in place with
  the enough freedom to deal with surprises on their own. Automation reduce ability to deal with surprises.
* **Sustained adaptability**: the ability to continually adapt to changing environments, stakeholders, and demands.
  Use **Chaos Engineering** to test it.

### How Much Is Too Much?

Understand the following requirements when considering if and how to scale out your system to better handle load and
falure:

* **Response time/latency**
* **Availability**: SLA, SLO, SLI
* **Durability of data**: recovery point objective (RPO), recovery time objective (RTO)

### Stability Patterns

* **Time-outs**. Define your timeout budget.
* **Retires**.
* **Bulkheads**: limit the impact of a failure (e.g. using different thread pools).
* **Circuit Breakers**.
* **Redundancy**.
* **Isolation**
* **Middleware**: e.g. message brokers.
* **Idempotency**

### CAP Theorem

* It's not all or nothing
* Getting multi-node consistency right is super hard.
* Strong consistency can not fix all problems when reflecting real world (lake of item in stock because of their local
  physical damage node yet reflected in the system).
* AP systems end up being the right call in many situations.

### Chaos Engineering

* Chaos Engineering is the discipline of experimenting on a distributed system in order to build confidence in the
  system's capability to withstand turbulent conditions in production.
* It's important that we see the systems as being the entirety of people, the processes, the culture and technology (
  software and infrastructure).
* Planning for failure is not the same as knowing that your system can handle failure.
* Incite failure to ensure that your system are tolerant of failure by running tools on it.

### Blame

* **Don't blame**, don't create culture of fear. **Learn** from mistakes, create a learning culture.
* Often the best learning can come in the wake of an incident.


