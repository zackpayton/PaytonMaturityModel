# PaytonMaturityModel
A basic (read: not one size fits all) consideration in Incident Response Readiness (maybe?)


What if we took the crown jewels of an organization and measured each environment on the following scale?

1. Level 0
* Zero or only tribal knowledge of the environment's technology infrastructure.
* Little to no documentation, or documentation that is in bad shape.
* No documented knowledge of available logs for the environment.
* No documented knowledge of Incident Response (IR) tools or process for the environment.

2. Level 1
* Document owners/security contacts of all operational teams involved.
* Identify and document what log sources are available to your equivelant of an IR team right now.
* Have a quick documented conversation with the teams about what IR looks like in their infrastructure taking care to note what special considerations apply. Let them know you're working on your security hygiene and how to contact you and if you plan to go farther in maturity that perhaps you're going to be working with them more to get additional security visibility and capabilities.
* Identify and document what response capabalities are available? Don't know AWS or docker forensics? Don't find out during a real incident.
* If applicable, best effort host and software inventory documentation of the environment.
* Links with descriptions to any documentation the team has.
* Find potential security champions or even infosec teams that have good relationships to help you.

3. Level 2
* Inventory systems owned by team.
* Document network topology of components.
* Identify and document what log sources would be useful for detections in that environment and take appropriate steps to acquire them.
* Identify and document what response capabilities are applicable to the environemnt and take steps to acquire them.
* If applicable, review former application security audits or vulnerability reports for the environment and document where to find them.
* If applicable, develop a basic threat model for the environment.
* Determine and document how applications are patched in the environment.
* Document behavior of administration (how is environment administered, where do admins log in from, what times of day?).

4. Level 3
* Start to build detections, alerting and response for low hanging fruit in the environment (like repeated authentication failures or just spikes in errors maybe depending on environment). This will help you figure out a process for analyzing alerts and responding to the environemnt. Figure out how to suppress false positives that occur frequently. Figure out how to enrich the alert with additional useful information that an analyst may frequently have to leave your IR workflow tool to retrieve.
* If applicable, mature your threat model and try to understand techniques used by attackers that could impact this particular crown jewel of the organization.
* Now that you have logs, build detections around known persistence mechanisms relevant to the environment. Check out Mitre At&ck for a start.
* If applicable document known scheduled tasks, applications, services, or drivers and suppress them, but alert on any new additions. This works much better in traditional server environments where software changes might occur less frequently.
* Purple team environment to drive detections for techniques that apply in the environment.
* Consider easy anomalies to detect such as weird admin login behavior, large network connections in/out of environment, or strange process behivour. 
* When applicapable, try to document network communication characteristics and consider building detections for anomalies (i.e. system reaching out to another system it's never talked to before).
* Start to develop alerting for when critical components fail to send logs.

5. Level 4
* Meet with team that administers component on a more regular basis for threat modeling and security excercises.
* Consider using an attack framework to automate attack unit tests to ensure your detections are working against real attacks.
* Red team environment on regular basis.
* Start considering how best to employ deception techniques in the environment.
* Level up your attack unit testing to conver a wide range the the Att&ck Matrix.

6. Level 5
* Mature deception networking setup.
* Consider trying to develop zero day for software used in the environment.
* Consider more advanced use cases for anomaly detection.
* Contract with top notch red teams or penetration test organizations to test environment.
