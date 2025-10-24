**Agile** is a philosophy. It emerged as a reaction to the slow, document-heavy, and inflexible Waterfall model that dominated software development before the 2000s. Waterfall treated projects as linear: gather all requirements first, design everything, build it, test it, and then deliver—often taking months or years before the customer saw anything usable. This led to waste, misaligned expectations, and frustration when late changes were needed.

Agile turns this model on its head. Instead of one long project, it promotes **iterative development**: you build a small part of the product, deliver it, get feedback, and then adjust. The core belief is that change is inevitable and even beneficial if handled properly. Agile is about shortening feedback loops, prioritizing value, and empowering teams to adapt continuously. It’s guided by the **Agile Manifesto** and its 12 principles, which emphasize collaboration, simplicity, and customer satisfaction.

However, Agile itself is not a process or a toolset—it’s a set of values. To apply it, teams need frameworks. **Scrum** is the most popular one.

Scrum takes Agile’s values and gives them a concrete structure. It defines specific roles, events, and artifacts to operationalize iteration and feedback. Work happens in **sprints**, short cycles (commonly 2–4 weeks) that each produce a usable product increment. The idea is that every sprint delivers something potentially releasable, reducing risk and making progress visible.

Three roles structure the process:

- The **Product Owner** manages the product backlog—an ordered list of features and improvements. They represent the customer’s interests and set priorities.
- The **Scrum Master** ensures the team follows Scrum rules, removes obstacles, and fosters continuous improvement.
- The **Development Team** (now simply called the _Developers_) actually build the product and decide how to turn backlog items into working increments.

Each sprint follows a rhythm:

1. **Sprint Planning** defines what will be done and sets a sprint goal.
2. **Daily Scrum** keeps everyone aligned and identifies blockers.
3. **Sprint Review** demonstrates the increment to stakeholders for feedback.
4. **Sprint Retrospective** examines the process and defines improvements.

These ceremonies enforce **transparency** (everyone sees the work and progress), **inspection** (frequent review of both product and process), and **adaptation** (course correction as needed).

While Scrum is the most structured Agile framework, others like **Kanban** or **Extreme Programming (XP)** offer different degrees of flexibility. Kanban, for example, focuses on continuous flow rather than fixed sprints; XP adds engineering practices like test-driven development and pair programming.


### **Agile — criticisms**

- **Buzzword misuse:** Many organizations claim to be “Agile” while keeping traditional hierarchies and fixed plans. This leads to “fake Agile” or “Agile in name only.”
- **Lack of predictability:** Iterative delivery makes long-term planning and budgeting harder for management used to fixed timelines.
- **Continuous change fatigue:** Constant reprioritization can exhaust teams and destabilize scope.
- **Overemphasis on meetings and collaboration:** Some developers see “Agile culture” as valuing discussion over deep work.
- **Scalability issues:** Agile works best for small, cross-functional teams. Scaling it across large enterprises (e.g., with SAFe) adds bureaucracy that negates its simplicity.

---

### **Scrum — criticisms**

- **Rigid rituals:** The prescribed events and roles can feel mechanical or excessive if applied dogmatically.
- **Dependency on skilled roles:** A weak Product Owner or Scrum Master can cause failure.
- **Velocity obsession:** Teams often get measured by sprint velocity instead of actual value delivered, leading to gaming metrics.
- **Limited flexibility mid-sprint:** Once a sprint starts, the backlog is frozen. In volatile environments, that can slow adaptation.
- **Team maturity assumption:** Scrum assumes self-organizing, motivated teams. Many organizations lack that culture, so Scrum becomes micromanagement in disguise.

---

### **Kanban**

Origin: Toyota Production System → applied to software by David J. Anderson.  
Core idea: visualize workflow, limit work in progress (WIP), and improve flow.

**Strengths**

- Simple to start with existing processes.
- Continuous delivery instead of sprint cycles.
- Strong focus on throughput, bottleneck detection, and flow efficiency.
- Suits operational and maintenance work where priorities shift often.

**Criticisms**

- Less guidance on roles, ceremonies, and planning.
- Without discipline, boards become cluttered and WIP limits ignored.
- Stakeholders may miss the sense of timeboxing and deadlines.
- Harder to measure progress in traditional project terms.

---

### **Extreme Programming (XP)**

Origin: Kent Beck, late 1990s. Focuses on engineering excellence inside Agile teams.

**Key practices**

- Test-Driven Development (TDD)
- Pair programming
- Continuous integration
- Refactoring
- Small releases
- Collective code ownership

**Strengths**

- Improves code quality and maintainability.
- Reduces defects early.
- Encourages continuous learning and feedback.

**Criticisms**

- Demanding discipline. Teams often drop hard practices like TDD or pair programming first.
- Perceived as costly: pair programming and constant testing reduce short-term output.
- Cultural mismatch: requires high trust and collaboration, rare in traditional organizations.
- Harder to justify to non-technical managers focused on immediate velocity.


In summary:

- **Agile** is the philosophy of iterative, customer-focused adaptability.
- **Scrum** is one of the most disciplined and widely used ways to enact it.
- Agile provides the mindset; Scrum provides the mechanics.