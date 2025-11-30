## MySQL Database Design

### Table: admin
- id: INT, Primary Key, Auto Increment
- name : VARCHAR(100) , NOT NULL 
- password: CHAR(60) , NOT NULL

  
### Table: Patient
- id: INT, Primary Key, Auto Increment
- name : VARCHAR(100) , NOT NULL 
- email : VARCHAR(100) , NOT NULL 
- password: CHAR(60) , NOT NULL

### Table: Doctor
- id: INT, Primary Key, Auto Increment
- name : VARCHAR(100) , NOT NULL 
- email : VARCHAR(100) , NOT NULL 
- password: CHAR(60) , NOT NULL
- clinic_location_id : INT , Foriegn Key → clinic_location(id)
  
### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)
  
### Table: payment
- id: INT, Primary Key, Auto Increment
- patient_id: INT, Foreign Key → patients(id)
- appointment_id:  INT, Foreign Key → appointment(id)
- amount:INT


### Table: clinic_location
- id: INT, Primary Key, Auto Increment
- name: VARCHAR(256),NOT NULL
- address:VARCHAR(256),NOT NULL
- landmark : VARCHAR(256)

## MongoDB Collection Design

### Collection: prescriptions
```json
{
  "_id": "ObjectId('64abc123456')",
  "patientName": "John Smith",
  "appointmentId": 51,
  "medication": "Paracetamol",
  "dosage": "500mg",
  "doctorNotes": "Take 1 tablet every 6 hours.",
  "refillCount": 2,
  "date" : "2025-02-12",
  "pharmacy": {
    "name": "Walgreens SF",
    "location": "Market Street"
  }
}
```

### Collection: prescriptions
```json
{ "_id" : "ObjectId('64abc123456')",
  "appointmentId": 51,
  "description":"something went wrong "
}
```

### Collection: messages
```json
{
  "_id": "ObjectId('675b0ac98abf')",
  "conversationId": "conv17821",     // chat between two people or group
  "senderId": "user123",
  "content": "Hi, the report is ready.",
  "type": "text",                    // text/image/audio/file
  "mediaUrl": null,                  // filled if type != text
  "reactions": [
    { "userId": "user456", "emoji": "👍", "reactedAt": "2025-11-29T12:15:00Z" }
  ],
}
  "status": "delivered",             // sent, delivered, seen
  "createdAt": "2025-11-29T12:00:00Z",
  "updatedAt": "2025-11-29T12:02:00Z"
}
```
