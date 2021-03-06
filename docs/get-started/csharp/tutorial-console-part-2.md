---
title: 'Tutorial: Extensión de una aplicación de consola de C# sencilla'
description: Aprenda a desarrollar una aplicación de consola de C# en Visual Studio mediante un procedimiento paso a paso.
ms.custom: get-started
ms.date: 07/09/2020
ms.technology: vs-ide-general
ms.prod: visual-studio-windows
ms.topic: tutorial
ms.devlang: CSharp
author: ghogen
ms.author: ghogen
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fd0d2b3e112a4bf08481fa8f043f70121d827010
ms.sourcegitcommit: cea9e5787ff33e0e18aa1942bf4236748e0ef547
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2020
ms.locfileid: "92197483"
---
# <a name="tutorial-extend-a-simple-c-console-app"></a>Tutorial: Extensión de una aplicación de consola de C# sencilla

En este tutorial, aprenderá a usar Visual Studio para extender la aplicación de consola que creó en la primera parte. Conocerá algunas de las características de Visual Studio que necesitará para el desarrollo diario, como administrar varios proyectos y hacer referencia a paquetes de terceros.

Si acaba de completar la [primera parte](tutorial-console.md) de esta serie, ya tiene la aplicación de consola de calculadora.  Para omitir la parte 1, abra el proyecto desde un repositorio de GitHub. La aplicación de calculadora de C# está en el [repositorio vs-tutorial-samples](https://github.com/MicrosoftDocs/vs-tutorial-samples), por lo que solo tiene que seguir los pasos que se describen en [Tutorial: Abrir un proyecto desde un repositorio](../tutorial-open-project-from-repo.md) para empezar.

## <a name="add-a-new-project"></a>Incorporación de proyecto nuevo

El código real está formado por numerosos proyectos que funcionan conjuntamente para dar lugar a una solución. Ahora, vamos a agregar otro proyecto a la aplicación de calculadora. Consiste en una biblioteca de clases que proporciona algunas de las funciones de la calculadora.

1. En Visual Studio, puede usar el comando del menú de nivel superior **Archivo** > **Agregar** > **Nuevo proyecto** para agregar un proyecto nuevo. También puede hacer clic con el botón derecho en el nombre del proyecto existente (denominado "nodo del proyecto") y abrir el menú contextual del proyecto. Este menú contextual contiene muchas maneras de agregar funcionalidad a los proyectos. Así pues, haga clic con el botón derecho en el nodo del proyecto en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto** .

1. Seleccione la plantilla de proyecto de C# **Biblioteca de clases (.NET Standard)** .

   ![Captura de pantalla de la selección de la plantilla de proyecto Biblioteca de clases](media/vs-2019/calculator2-add-project-dark.png)

1. Escriba el nombre del proyecto **CalculatorLibrary** y seleccione **Crear** . Visual Studio crea el proyecto y lo agrega a la solución.

   ![Captura de pantalla del Explorador de soluciones con el proyecto de biblioteca de clases CalculatorLibrary agregado](media/vs-2019/calculator2-solution-explorer-with-class-library-dark2.png)

1. En lugar de dejar el nombre de archivo *Class1.cs* , cámbielo a **CalculatorLibrary.cs** . Puede hacer clic en el nombre en el **Explorador de soluciones** para cambiarlo, o bien hacer clic con el botón derecho y seleccionar **Cambiar nombre** . Otra opción es presionar la tecla **F2** .

   Es posible que se le pregunte si quiere cambiar el nombre de las referencias a `Class1` en el archivo. No importa qué responda en este momento, ya que reemplazará el código en un paso posterior.

1. Ahora debemos agregar una referencia de proyecto para que el primer proyecto pueda usar las API que expone la nueva biblioteca de clases.  Haga clic con el botón derecho en el nodo **Referencias** del primer proyecto y seleccione **Agregar referencia de proyecto** .

   ![Captura de pantalla del elemento de menú Agregar referencia de proyecto](media/vs-2019/calculator2-add-project-reference-dark.png)

   Aparecerá el cuadro de diálogo **Administrador de referencias** . Este cuadro de diálogo permite agregar referencias a otros proyectos, así como los ensamblados y las DLL COM que los proyectos necesiten.

   ![Captura de pantalla del cuadro de diálogo Administrador de referencias](media/vs-2019/calculator2-ref-manager-dark.png)

1. En el cuadro de diálogo **Administrador de referencias** , active la casilla correspondiente al proyecto **CalculatorLibrary** y seleccione **Aceptar** .  La referencia del proyecto aparece en un nodo **Proyectos** en el **Explorador de soluciones** .

   ![Captura de pantalla del Explorador de soluciones con una referencia de proyecto](media/vs-2019/calculator2-solution-explorer-with-project-reference-dark2.png)

1. En *Program.cs* , seleccione la clase `Calculator` y todo su código, y presione **CTRL+X** para cortarla de Program.cs. Después, en **CalculatorLibrary** , en *CalculatorLibrary.cs* , pegue el código en el espacio de nombres `CalculatorLibrary`. Posteriormente, haga que la clase Calculator `public` lo exponga fuera de la biblioteca. El código de *CalculatorLibrary.cs* ahora debería ser similar al siguiente:

   ```csharp
   using System;

    namespace CalculatorLibrary
    {
        public class Calculator
        {
            public static double DoOperation(double num1, double num2, string op)
            {
                double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.

                // Use a switch statement to do the math.
                switch (op)
                {
                    case "a":
                        result = num1 + num2;
                        break;
                    case "s":
                        result = num1 - num2;
                        break;
                    case "m":
                        result = num1 * num2;
                        break;
                    case "d":
                        // Ask the user to enter a non-zero divisor.
                        if (num2 != 0)
                        {
                            result = num1 / num2;
                        }
                        break;
                    // Return text for an incorrect option entry.
                    default:
                        break;
                }
                return result;
            }
        }
    }
   ```

1. El primer proyecto tiene una referencia, pero verá un error que la llamada a Calculator.DoOperation no resuelve. Esto se debe a que CalculatorLibrary está en un espacio de nombres diferente, por lo que debe agregar el espacio de nombres `CalculatorLibrary` para obtener una referencia completa.

   ```csharp
   result = CalculatorLibrary.Calculator.DoOperation(cleanNum1, cleanNum2, op);
   ```

   Pruebe a agregar una directiva using al principio del archivo:

   ```csharp
   using CalculatorLibrary;
   ```

   Este cambio debería permitirle quitar el espacio de nombres CalculatorLibrary del sitio de llamada, pero ahora hay una ambigüedad. ¿Es `Calculator` la clase de CalculatorLibrary, o es Calculator el espacio de nombres?  Para resolver la ambigüedad, cambie el nombre del espacio de nombres a `CalculatorProgram`.

   ```csharp
   namespace CalculatorProgram
   ```

## <a name="reference-net-libraries-write-to-a-log"></a>Referencia a bibliotecas de .NET: escritura en un registro

1. Supongamos que ahora quiere agregar un registro de todas las operaciones y escribirlo en un archivo de texto. La clase `Trace` de .NET proporciona esta funcionalidad. (También es útil para las técnicas básicas de impresión de la depuración).  La clase Trace se encuentra en System.Diagnostics, y se necesitan clases System.IO como `StreamWriter`, así que empiece por agregar las directivas Using:

   ```csharp
   using System.IO;
   using System.Diagnostics;
   ```

1. Si observa cómo se usa la clase Trace, es necesario mantener una referencia para la clase, que está asociada a una secuencia de archivos. Esto significa que la calculadora funcionaría mejor como un objeto, por lo que vamos a agregar un constructor.

   ```csharp
   public Calculator()
        {
            StreamWriter logFile = File.CreateText("calculator.log");
            Trace.Listeners.Add(new TextWriterTraceListener(logFile));
            Trace.AutoFlush = true;
            Trace.WriteLine("Starting Calculator Log");
            Trace.WriteLine(String.Format("Started {0}", System.DateTime.Now.ToString()));
        }

    public double DoOperation(double num1, double num2, string op)
        {
   ```

1. Además, hay que cambiar el método `DoOperation` estático a un método de miembro.  Vamos a agregar también una salida a cada cálculo para el registro, de modo que DoOperation tendrá un aspecto similar al del código siguiente:

   ```csharp
   public double DoOperation(double num1, double num2, string op)
   {
        double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.

        // Use a switch statement to do the math.
        switch (op)
        {
            case "a":
                result = num1 + num2;
                Trace.WriteLine(String.Format("{0} + {1} = {2}", num1, num2, result));
                break;
            case "s":
                result = num1 - num2;
                Trace.WriteLine(String.Format("{0} - {1} = {2}", num1, num2, result));
                break;
            case "m":
                result = num1 * num2;
                Trace.WriteLine(String.Format("{0} * {1} = {2}", num1, num2, result));
                break;
            case "d":
                // Ask the user to enter a non-zero divisor.
                if (num2 != 0)
                {
                    result = num1 / num2;
                    Trace.WriteLine(String.Format("{0} / {1} = {2}", num1, num2, result));
                }
                    break;
            // Return text for an incorrect option entry.
            default:
                break;
        }
        return result;
    }
   ```

1. Ahora, de nuevo en Program.cs, la llamada estática está marcada con una línea ondulada roja. Para corregirlo, cree una variable `calculator` mediante la incorporación de la línea siguiente justo antes del bucle while:

   ```csharp
   Calculator calculator = new Calculator();
   ```

   Modifique el sitio de llamada para `DoOperation` como se indica a continuación:

   ```csharp
   result = calculator.DoOperation(cleanNum1, cleanNum2, op);
   ```

1. Vuelva a ejecutar el programa y, cuando haya terminado, haga clic con el botón derecho en el nodo del proyecto y elija **Abrir la carpeta en el Explorador de archivos** . Luego, desplácese hacia abajo en el Explorador de archivos a la carpeta de salida. Podría ser *bin/Debug/netcoreapp3.1* . Abra el archivo *calculator.log* .

    ```output
    Starting Calculator Log
    Started 7/9/2020 1:58:19 PM
    1 + 2 = 3
    3 * 3 = 9
    ```

## <a name="add-a-nuget-package-write-to-a-json-file"></a>Incorporación de paquete NuGet: escritura en un archivo JSON

1. Supongamos ahora que queremos generar las operaciones en JSON, un formato popular y portable para almacenar datos de objeto. Para implementar esta funcionalidad, es necesario hacer referencia al paquete NuGet Newtonsoft.Json. Los paquetes NuGet son el vehículo principal para la distribución de bibliotecas de clases .NET. En el **Explorador de soluciones** , haga clic con el botón derecho en el nodo **Referencias** del proyecto CalculatorLibrary y seleccione **Administrar paquetes NuGet** .

   ![Captura de pantalla del menú contextual Administrar paquetes NuGet](media/vs-2019/calculator2-manage-nuget-packages-dark2.png)

   Se abrirá el administrador de paquetes NuGet.

   ![Captura de pantalla del Administrador de paquetes NuGet](media/vs-2019/calculator2-nuget-package-manager-dark.png)

1. Busque el paquete Newtonsoft.Json y seleccione **Instalar** .

   ![Captura de pantalla de la información del paquete NuGet Newtonsoft](media/vs-2019/calculator2-nuget-newtonsoft-json-dark2.png)

   El paquete se descarga, se agrega al proyecto y aparece una nueva entrada en el nodo Referencias del **Explorador de soluciones** .

1. Agregue una directiva Using del paquete System.IO y Newtonsoft.Json al principio de *CalculatorLibrary.cs* .

   ```csharp
   using Newtonsoft.Json;
   ```

1. Ahora, reemplace el constructor para Calculator por el código siguiente y cree el objeto de miembro JsonWriter:

   ```csharp
        JsonWriter writer;

        public Calculator()
        {
            StreamWriter logFile = File.CreateText("calculatorlog.json");
            logFile.AutoFlush = true;
            writer = new JsonTextWriter(logFile);
            writer.Formatting = Formatting.Indented;
            writer.WriteStartObject();
            writer.WritePropertyName("Operations");
            writer.WriteStartArray();
        }
   ```

1. Modifique el método `DoOperation` para agregar el código del escritor de JSON:

   ```csharp
        public double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error.
            writer.WriteStartObject();
            writer.WritePropertyName("Operand1");
            writer.WriteValue(num1);
            writer.WritePropertyName("Operand2");
            writer.WriteValue(num2);
            writer.WritePropertyName("Operation");
            // Use a switch statement to do the math.
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    writer.WriteValue("Add");
                    break;
                case "s":
                    result = num1 - num2;
                    writer.WriteValue("Subtract");
                    break;
                case "m":
                    result = num1 * num2;
                    writer.WriteValue("Multiply");
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor.
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                        writer.WriteValue("Divide");
                    }
                    break;
                // Return text for an incorrect option entry.
                default:
                    break;
            }
            writer.WritePropertyName("Result");
            writer.WriteValue(result);
            writer.WriteEndObject();

            return result;
        }
   ```

1. Deberá agregar un método para finalizar la sintaxis JSON una vez que el usuario haya acabado de escribir los datos de la operación.

   ```csharp
    public void Finish()
    {
        writer.WriteEndArray();
        writer.WriteEndObject();
        writer.Close();
    }
   ```

1. En *Program.cs* , agregue una llamada a Finish al final.

   ```csharp
            // And call to close the JSON writer before return
            calculator.Finish();
            return;
        }
   ```

1. Compile y ejecute la aplicación y, cuando acabe de escribir algunas operaciones, cierre la aplicación correctamente con el comando "n".  Ahora abra el archivo calculatorlog.json. Debería ver algo parecido a lo siguiente:

   ```json
   {
    "Operations": [
        {
        "Operand1": 2.0,
        "Operand2": 3.0,
        "Operation": "Add",
        "Result": 5.0
        },
        {
        "Operand1": 3.0,
        "Operand2": 4.0,
        "Operation": "Multiply",
        "Result": 12.0
        }
    ]
   }
   ```

## <a name="next-steps"></a>Pasos siguientes

Enhorabuena por completar este tutorial. Para más información, continúe con los tutoriales siguientes.

> [!div class="nextstepaction"]
> [Continuar con más tutoriales de C#](/dotnet/csharp/tutorials/)

> [!div class="nextstepaction"]
> [Continuar con la introducción al IDE de Visual Studio](/../visual-studio-ide.md)

## <a name="see-also"></a>Vea también

* [IntelliSense para C#](../../ide/visual-csharp-intellisense.md)
* [Información sobre cómo depurar código de C# con Visual Studio](tutorial-debugger.md)
