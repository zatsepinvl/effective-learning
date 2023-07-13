# Building Microservices

by Sam Newman

## 8. Deployment

### Principles of Microservice Deployment

* **Isolated execution** - microservices don't share computing resources. Microservices can not impact other instances
  running nearby.
* **Focus on automation** - automate everything.
* **Infrastructure as Code** - store infrastructure configuration in source control. Use right tools: Terraform, Pulumi,
  Puppet, Chef, Ansible.
* **Zero-Downtime Deployment** - deploy new version of a microservice without any downtime to users or other dependent
  systems.
* **Desired state management** - use a platform that maintains your microservices in a defined state (number of
  instances,
  allocated resources).

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
* Practice:  **Feature Flags** - enable/disable feature in production using flag boolean variables.
* Practise: **Canary Releases** - roll-out new functionality for users gradually.
* Practise: **Parallel Runs** - run different implementations of the same microservice side by side, send requests to
  both and then compare the
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

## 13. Scaling

Reasons:

1. Improve latency or handle more load
2. Improve robustness

### Four axes of scaling

1. **Vertical**  (scale up/down) - getting a bigger machine. On virtualized infrastructure (public cloud), it will be
   fast. My be limited by software not using all the CPU cores. No improvement in robustness. Having larger number of
   small machines might be more cost-effective than to have a small number of large machines.
2. **Horizontal duplication** (scale in/out) - more instances. Implemented by using load balancer or **competing
   consumer pattern**. Relatively straightforward, but requires more infrastructure.
3. **Data partitioning** - dividing work based on partition strategy. Database partition makes sense if it is supported
   natively. Scales nicely for transactional workloads. Requires throughout choice of partition key. Might hit an issue
   with queries that span the data in multiple nodes (e.g. MongoDB uses map-reduce to perform such queries). Tricky
   scaling for writes.Requires more work than vertical/horizontal scaling.
4. **Functional decomposition** - separation of work into different microservices and scaling them separately. See
   microservice functional decomposition for implementation details. Enables balancing of infrastructure costs, thereby
   helping to drive profitability. Also helps to scale an organization. Increases overall complexity of the system. Try
   to exhaust the other options before considering this one.

### Combining Models

Scale along multiple axes.

### Start Small

We tend to worry too much about efficiency in the wrong places and at the wrong times.
Ensure that we have a system that is needlessly more complex. Use incremental process of experimentation. See
Sustainable Adaptability in Resilience.

### Caching

:exclamation: **Treat caching as optimization. The best caching is zero caching.**

Use cache for:

1. Performance - decrease latency
2. Scale, e.g. database read replicas as cache mechanism.
3. Robustness - data in local cache enables you to operate in case of origin outage (be careful with the level of stale
   cache tolerance)

Places to cache:

1. **Client side** - reduced number of request hops.
2. **Server side** - reduced latency.

Invalidation mechanisms:

1. **Time to live** - entry level timestamp or HTTP headers (Cache-Control, Expires). Simplicity of implementation needs
   to
   be balanced against how much tolerance you have around operating on out-of-date data.
2. **Conditional GETs** - use ETag HTTP header to conditionally make query to data source.
3. **Notification base** - client-side cache with update-cache events from data source. Elegant, but requires additional
   middleware as message broker to implement. Use heartbeat mechanism as fall-back for invalidation in case of broken
   message delivery or source outage.
4. **Write-through** - the cache is updated at the same time as the state in the origin. Complex, thus used on
   server-side.
5. **Write-behind** - the cache itself is updated first, and then the origin is. Cache works like a buffer. Potential
   data
   loss is a big concern. Not clear what the origin and source of truth are. Often used for in-process optimizations,
   but more rarely in microservices.

**The golden rule of caching**:

1. The more caches between you and the source of fresh data, the more stale the data can be.
2. Do not cache on client and server sides in the same time. Be aware of **cache poisoning**.
3. Caching right is complex. The ideal number of places to cache is zero.

Freshness vs optimization: understand the requirements of the end user and of the wider system to balance between data
freshness and latency/performance.

### Autoscaling

Two types:

1. **Predictive** - scale by well-known load trends (e.g. peak load times in the morning for a news website).
2. **Reactive** - bring up additional instances when see:
    1. an increase in load
    2. an instance failure

Have a good suite of **load tests** to reproduce different loads for reactive autoscaling.
**Use autoscaling for failure conditions first** while you collect the data to implement scaling for load right.
Make sure that you very cautious about **scaling down too quickly**. In most situations, having more computing power at
hand than you need is much better than not having enough.

### Start Again

Avoid **starting from scratch** idea. That is a danger that people will see the need to rearchitect when certain scaling
thresholds are reached as a reason to build for massive scale from the beginning.

As always, start with simple, rapidly experiment and understand required capabilities.

The need to change our systems to deal with scale isn't a sign of failure. It is a sign of success.

## 14. User Interfaces

Think of user interfaces as the places where we weave together the various strands of the capabilities we want to offer
our users.

### Ownership Models

**Dedicated frontend team**. Drivers: scarcity of specialists, a drive for consistency, technical challenges. Drawback:
any UI change requires a constant coordination and handing off work between teams (frontend, backend).

**Stream-aligned teams** or _full-stack team_. UI broken apart and managed by a stream-aligned team including
server-side components. Teams have direct, component-facing responsibilities in terms of the software they deliver.
Ensure UI/UX consistency across feature teams _enabling teams_ to share specialist and expertise (feature-agnostic, e.g.
platform or UX designers team). Don't be afraid of work overlapping or duplication sometimes between product teams, we
pay a fair price for the increased autonomy and the spead of delivery will pay it off.
(:exclamation) When you are more removed from the end user, it becomes harder to understand whether your contributions
are successful, and you can end up focusing on goals that are a long way removed from things the people using your
software care about.

### Pattern: Monolithic Frontend

UI is a solid deployable unit in which all the UI state and behaviour is defined in the UI itself.
Use it when already have a dedicated frontend team.

### Pattern: Micro Frontends

An architectural style where independently deliverable frontend applications are composed into a greater whole.

Use when want to adopt end-to-end, steam-aligned teams to benefit the most from the microservice architecture.

**Page-based decomposition**.

UI is decomposed into multiple web pages (not SPA). Requires common navigation to help stitch pages together.
Simplicity of the technical implementation is a real appeal. The user clicks a link, and a new page is requested.

**Widget-based decomposition**.

SPA contains widgets that cna be changed independently. Requires a container application that defines things like the
navigation.

Be aware of widgets' dependency duplication and version conflicts. Make an effort to reduce the size of the final
bundle.

This pattern makes it easy for multiple stream-aligned teams to contribute to the same UI.
Know the constraints: might be hard to apply for mobile app because of device variety and accessibility consistency.

### Pattern: Central Aggregating Gateway

The way to optimize client-server API communication in case of network issues on mobile devices (latency, network
contention, lack of stable connection).

Central gateway exposes aggregation and filtering capabilities driven by UI (client) needs.

Fundamentally, due to centralized nature, ends up with all teams making changes into the gateway, thereby leading to
contention and bottleneck. On the other hand, a single team owning the gateway becomes a bottleneck when it comes to
delivery.

If you use API Gateway, do not put your domain specific filtering and aggregation logic there.

> When customizing a product build by someone else, you often have to work in THEIR world, not yours. Your toolchain is
> restricted because you may not be able to use your programming language and your development practises. Configuring
> that tool in some odd product-specific DSL might be a frustrating experience.

### Pattern: Backend for Frontend (BFF)

Each "experience" (like web and mobile, or desktop and wearable devices) has its own server exposing client driven
aggregation and filtering API capabilities.

If BFF is the choice, code duplication is inevitable, but eschew building common library to share some code among
multiple BFFs as **a
shared libraries are a prime source of coupling**.

The pattern might also be used for exposing external system driven API (not necessarily user interface)

### GraphQL

Use to implement aggregation gateway or BFF to be able to change queries without changing the server side (to some
extent).

### A Hybrid Approach

All the patterns don't need to be one-size-fits-all solutions.
But **retain cohesion of the underlying capabilities**: don't allow a feature specific logic to get smeared all over
your system.
Avoiding the trap of putting too much behaviour into any
intermediate layer (aggregation gateway) is a tricky balancing act.

## 16. The Evolutionary Architect

Core responsibilities of the evolutionary architect:

* **Vision** - Ensture there is a clearly communicated technical vision for the system.
* **Empathy** - Understand the impact of your decision on your customers and colleagues.
* **Collaboration** - Engage with as many of your peers and colleagues as possbile to help define, refine, and execute the vision.
* **Adaptability** - Make sure that the technical vision changes as required by your customers or organization.
* **Atonomy** - Find the right balance between standardizing and enabling autonomy for your teams.
* **Governance** - Ensure that the system being implemented fits the technical vision, and make sure it is easy for people to do the right thing.

> Rules are for the obedience of fools and the guidance of wise men. - Generally attributed to Douglas Bader.

Governance and The Paved Road techniques:

* **Platform** - The architect ends up being an important stakeholder for the platform team.
* **Examplars** - Real-world microservice running in your system that get things right.
* **Tailoed Microservice Template**. Caution: should be provided for each tech stack used across all teams.
  
### What Is Software Architecture

❗ Architecture is shared understanding that includes how the system is devided into components and how the components interact through interfaces.
Atchitecture is a social construct, because it doesn't just depend on the software, but on what part of the software is considered important by group consensus.

❗ As a architect, don't limit the scope of what you care about, because it limits your ability to reason and make changes.

### Makeing Change Possible

📖 [Seagram_Building](https://en.wikipedia.org/wiki/Seagram_Building) was developed using a process in which the design of the building evolved while the construction was carried out. The architects focused on finding a space for core services that would be difficult if not impossbile to change later, but also had to ensure that the building could be used in different ways than originally envisaged.

### An Evolutionary Vision for the Architect

* Focus on building a **framework** where the right system can emerge and continue to grow as we learn more.
* Be highly specific about implementation detail only in limited cases.
* Ensure that the system is fit for purpose now but also a **platform** for the future.

### Defining System Boundaries

* Create space for change at large-scope levels.
* Be worried about what happens between the boxes, and be liberal in what happens inside. Because it must be freedome for teams to lead their technical decisions but guidance between microservices where things can get messy.

### A Social Construct

* 💡 Vision is what planned, artchitecture is what happens.
* Eventualy architecture is a reflection of the billions upon billions of small and large, intentional and accidential design decisions made along thw way.
* Successful architecture is a team effort.
* 💡 Greate software comes from great people. ❗ If you worry only about the technology, you are missing way more than half of the picture.
* Help people to grow.

### Habitability

* Ensure that the environment you create is nice to work in.
* Understand the impact of the technical decision on teams and their mental wellbeing.
* Make spending time with the team as a routine activity.

### A Principled Approach

* Principles are global rules. Principles frame technical decision making to align it with business strategic goals. 
* Practises are set of detailed, practical guidlines for performing tasks. Practises underpin principles.
* Principles and practises change but with different frequency, as the former are more rigid.
<img width="704" alt="image" src="https://github.com/zatsepinvl/effective-learning/assets/11683340/1eea3213-17e5-487c-b80a-2527c75bc68e">




