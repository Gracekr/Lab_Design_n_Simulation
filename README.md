# Lab_Design_n_Simulation
Part 1: Designing Cloud Infrastructure
Para hacer esta aplicación Web escalable usaría:
•	EC2 para mantener las máquinas virtuales y allí correría mi aplicación.
•	S3 para el almacenamiento de datos estáticos.
•	VPC para conectar los servidores y mantener la seguridad.
•	RDS para gestionar las bases de datos relacionales.
•	CloudWatch para monitoreo.

Part 2: IAM Configuration
Roles:
•	Rol de administrador: tiene acceso a todo.
•	Rol de desarrollador: Puede leer los logs. No puede borrar

Part 3: Resource Management Strategy
Como estrategia haría seguimiento del tráfico de manera de que si hay épocas de muchas visitas se agreguen mas servidores y si baja el tráfico se apagarían algunos. Balancearía las cargas entre servidores para que no colapsen. 

Part 4: Theoretical Implementation
ELB balancea las cargas, entonces se comunica con EC2. A su vez EC2 requiere los datos guardados con S3. Y el AutoScaling crea mas instancias en función de la demanda, así que se comunica con EC2.

Part 5: Discussion and Evaluation
Los roles IAM se definieron de manera que pueda distribuirse la carga de responsabilidad y la seguridad. Dando al Rol de Administrador una responsabilidad importante para que pueda controlar la aplicación, siempre que pase los niveles de seguridad en el acceso. Y al developer, se le dan los permisos estrictamente necesarios para que se enfoque en desarrollo. 
El ahorro en costos se manifiesta en usar los servidores a demanda, según el tráfico que tenga nuestra aplicación. 
Los servicios escogidos, son los básicos para que la aplicación funcione correctamente. Ofrecen las prestaciones necesarias para que la aplicación sea escalable, se pueda monitorizar y no colapse.
