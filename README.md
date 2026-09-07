# Pr-ctica-3---La-Capa-de-Dominio-con-Gen-ricos-y-Patrones

1. ¿Hizo falta una base de datos real para probar la regla de negocio? No, no hizo falta una base de datos real. Se pudo probar la regla usando el repositorio en memoria.
   ¿Qué dice eso sobre para qué sirve el patrón Repository? Esto demuestra que el patrón Repository sirve para separar la forma en que se guardan los datos de la lógica del programa.
   
3. El Service recibe el repositorio como Repository<Prestamo>, no InMemoryPrestamoRepository. ¿Qué se rompía si usaban la clase concreta?
   Si usáramos InMemoryPrestamoRepository, el Service dependería directamente de esa clase. Entonces si después cambiamos la forma de guardar los datos, tendríamos que modificar el Service. Con Repository<Prestamo> solo         depende de lo que el repositorio puede hacer.
   
4. Si cambiaran el Map en memoria por una base de datos real, ¿cuántos archivos tocarían? ¿Por qué tan pocos?
   Solo tendríamos que cambiar principalmente el archivo del repositorio y main.ts, donde se crea el repositorio. Son pocos archivos porque el Service no depende de cómo se guardan los datos, solo depende de la interfaz        PrestamoRepository.
