Analiza la Tabla Summinstrada
-
![alt text](image.png)
Analizando la tabla puedo deducir que la CitaID como clave primaria porque identifica de forma única cada cita médica registrada en la tabla, evitando duplicados x|y permitiendo ver cada registro individual.

Observacion:  
Si la tabla no tuviera CitaID, podrías usar una clave compuesta, por ejemplo:
- PacienteID
- FechaCIT

Identificar las Dependencias Funcionales Existentes.
-----------

PacienteID determina los datos del paciente  
1. PacienteID → NombrePaciente, TelefonoPaciente, CiudadPaciente
![alt text](<Captura de pantalla 2026-06-12 012032.png>)
2. MedicoID → NombreMedico, Especialidad, Consultorio
![alt text](<Captura de pantalla 2026-06-12 012155.png>)
3. Consultorio → PisoConsultorio, Fechas
![alt text](<Captura de pantalla 2026-06-12 012235.png>)


Aplicar Primera Forma Normal (1FN), (2FN), (3FN)
-
1FN:   
La tabla sí cumple la Primera Forma Normal (1FN) porque todos las celdas no existen grupos repetitivos.

2FN:    
deben depender completamente de la clave primaria.    
Sin embago hay depedencias  

PacienteID → NombrePaciente, TelefonoPaciente, CiudadPaciente   
MedicoID → NombreMedico, Especialidad, Consultorio  
Consultorio → PisoConsultorio

3FN:   
No deben tener dependencias transitivas.  

CitaID → MedicoID → NombreMedico  
CitaID → MedicoID → Especialidad  
CitaID → Consultorio → PisoConsultorio  
CitaID → PacienteID → NombrePaciente  
La tabla NO cumple la Tercera Forma Normal (3FN) porque existen dependencias transitivas entre los atributos. Los datos de pacientes, médicos y consultorios deberían almacenarse en tablas separadas para evitar redundancia y anomalías de actualización.