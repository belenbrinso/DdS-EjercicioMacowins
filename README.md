# DdS-EjercicioMacowins
Ejercicio para la materia Diseño de Sistemas, curso K3053

Requerimientos:
  - Saber el precio de venta de una prenda y su tipo.
  - Saber las ganancias de un determinado día.

Solución propuesta:

![DdS - Ejercicio Macowins](https://user-images.githubusercontent.com/81327732/231801403-2d3350ee-1aa9-4089-97c2-de3be79675a2.png)

Aclaraciones:
  - En esta instancia los tipos de prendas no se usan para nada, por eso elijo modelarlos como strings, por ejemplo.
  - El coeficiente fijo que se usa en el recargo de la tarjeta no lo modelé como un atributo de esa clase porque no queda muy claro de dónde lo obtenemos, puede ser un valor x que la empresa cambia cada año y no depende de la tarjeta uso para pagar.
  - Podríamos tener una clase Registro que posea una lista de Fecha, pero no la modelé porque en esta instancia no hacemos nada con dicha clase.
  - Pseudocódigo que considero necesario para terminar de entender el diagrama de clases:
        
        PRENDA:
        precio() {
               estado.descuento(precioLista)
        }

        ITEMVENTA:
        precioItem() {
                prenda.precio() x cantidad
        }

        VENTA:
        precioFinal() {
                 precioTotal() + tipoCobro.recargo(listaItems)
        }

        TARJETA:
        recargo(listaItems) {
                 adicionalPrendas = listaItems.sumar{ item => item.precioItem() * 0,01 * item.cantidad }
                 cantidadCuotas * coefFijo + adicionalPrendas
        }

        FECHA:
        ganancia() {
                 ventas.sumar{ venta => venta.precioTotal() }
        }
