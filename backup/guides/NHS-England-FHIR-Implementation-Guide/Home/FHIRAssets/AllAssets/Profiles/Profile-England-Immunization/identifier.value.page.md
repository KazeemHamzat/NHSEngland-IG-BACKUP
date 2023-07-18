## `identifier.value`

<b>Definition</b><br>

A unique identifier for the vaccination record, that is consistent between any subsequent update or delete records.

Ideally this would be a GUID / UUID

Value in combination with UNIQUE_ID_URI must be globally unique
In other words, a combination of `identifier.value` and `identifier.system` act as composite primary key to allow lookup of any Adverse Reactions records from the corresponding Adverse Reaction data file.

1) UUID example:
`e045626e-4dc5-4df3-bc35-da25263f901e`

2) Example of a “single instance for all customers” Supplier system
`ACME-vacc123456`

3) Example of “per customer instance” Supplier system
`ACME-CUSTOMER1-vacc123456`
`ACME-CUSTOMER2-vacc123456`

---