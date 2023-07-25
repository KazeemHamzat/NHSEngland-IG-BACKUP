## `status`

<b>Definition:</b><br>

These workflow tasks have status which indicates the Task status.

The following diagram reflects the "typical" state machine for Task. Note that not all states will be supported by all workflows and that some workflows may support additional transitions, including transitions from terminal states (e.g. back to "in-progress" from "failed" or "completed").

<br>

<img src="https://www.hl7.org/fhir/task-state-machine.svg"></img>

---

For example: <br>
A patient requesting a repeat prescription would ask for task with code `fulfil` used with `103742009 | Renewal of prescription` and a status of `requested`. <br>
Once reviewed (by a clinician), the task status would be changed to `accepted`. When the task is then picked up (`in-progress`) and the related *MedicationRequest* is sent, the status would change to `completed`.

 #### Comment

 For **EPS**

Only `in-progress` is currently supported for reasonCode = 373784005 (Dispensing medication) and focus is a `dispense-notification`. 

`rejected` / `cancelled` / `failed` are supported for reasonCode = 33633005 (Prescription of drug) and focus is a `prescription-order`.

---