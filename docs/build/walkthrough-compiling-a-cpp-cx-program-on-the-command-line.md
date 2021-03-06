---
title: Пошаговое руководство. Компиляция программы на языке C++/CX из командной строки
ms.date: 04/23/2019
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
ms.openlocfilehash: 8dcd27ca8fff826f33ee8bd752cd32f2d44d3691
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836716"
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>Пошаговое руководство. Компиляция программы на языке C++/CX из командной строки

> [!NOTE]
> Для новых приложений и компонентов UWP рекомендуется использовать [C++/WinRT](/windows/uwp/cpp-and-winrt-apis/), стандартную проекцию языка C++17 для API среды выполнения Windows. C++/WinRT доступна в пакете SDK для Windows 10, начиная с версии 1803. C++/WinRT реализована полностью в файлах заголовков и предназначена для предоставления доступа к современным API Windows через первый класс.

Компилятор Microsoft C++ (MSVC) поддерживает расширения компонентов Visual C++ (C++/CX) с дополнительными типами и операторами, предназначенными для программной модели среды выполнения Windows. Можно использовать C++/CX для создания приложений для универсальной платформы Windows (UWP) и классических приложений для Windows. Дополнительные сведения см. в статьях [Знакомство с C++/CX](/archive/msdn-magazine/2013/april/component-extensions-a-tour-of-c-cx) и [Расширения компонентов для платформ среды выполнения](../extensions/component-extensions-for-runtime-platforms.md).

В этом руководстве мы используем текстовый редактор для создания простой программы C++/CX, а затем компилируем эту программу в командной строке. (Можно использовать вашу собственную программу C++/CX вместо ввода показанной здесь, или же можно использовать образец кода C++/CX из другой статьи справки. Эта методика полезна для сборки и тестирования небольших модулей, не содержащих элементы пользовательского интерфейса.)

> [!NOTE]
> В интегрированной среде разработки (IDE) Visual Studio также можно компилировать программы C++/CX. Интегрированная среда разработки включает средства проектирования, отладки, имитации и поддержки развертывания, недоступные в командной строке, поэтому мы рекомендуем использовать интегрированную среду разработки для создания приложений для универсальной платформы Windows (UWP). Дополнительные сведения см. в разделе [Создание приложения UWP на C++](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp).

## <a name="prerequisites"></a>Предварительные требования

Для работы необходимо владеть основами языка C++.

## <a name="compiling-a-ccx-program"></a>Компиляция программы на C++/CX

Чтобы включить компиляцию для C++/CX, нужно использовать параметр компилятора [/ZW](reference/zw-windows-runtime-compilation.md). Компилятор MSVC создает файл EXE, предназначенный для среды выполнения Windows и связанный с необходимыми библиотеками.

#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>Компиляция приложения C++/CX из командной строки

1. Откройте окно **Командная строка разработчика**. (В меню **Пуск** выберите пункт **Приложения**. Откройте папку **Visual Studio Tools** для соответствующей версии Visual Studio, а затем выберите ярлык **Командная строка разработчика**.) Дополнительные сведения об открытии командной строки разработчика см. в статье [Использование набора инструментов MSVC из командной строки](building-on-the-command-line.md).

   В зависимости от операционной системы и конфигурации компьютера для успешной компиляции кода могут потребоваться учетные данные администратора. Чтобы запустить окно командной строки от имени администратора, щелкните правой кнопкой мыши элемент **Командная строка разработчика** и выберите команду **Запуск от имени администратора**.

1. В командной строке введите следующую команду: **notepad basiccx.cpp**.

   Когда появится запрос на создание файла, нажмите кнопку **Да**.

1. В Блокноте введите следующие строки:

    ```cpp
    using namespace Platform;

    int main(Platform::Array<Platform::String^>^ args)
    {
        Platform::Details::Console::WriteLine("This is a C++/CX program.");
    }
    ```

1. В строке меню выберите **Файл** > **Сохранить**.

   Вы создали файл исходного кода C++, который использует [пространство имен платформы](../cppcx/platform-namespace-c-cx.md) среды выполнения.

1. В командной строке введите следующую команду: **cl /EHsc /ZW basiccx.cpp /link /SUBSYSTEM:CONSOLE**. Компилятор cl.exe скомпилирует исходный код в OBJ-файл, а затем запустит компоновщик для создания исполняемой программы с именем basiccx.exe. (Параметр компилятора [/EHsc](reference/eh-exception-handling-model.md) указывает модель обработки исключений C++, а параметр [/link](reference/link-pass-options-to-linker.md) указывает консольное приложение.)

1. Чтобы запустить программу basiccx.exe, в командной строке введите **basiccx**.

   Программа выводит следующий текст и закрывается:

    ```Output
    This is a C++/CX program.
    ```

## <a name="see-also"></a>См. также

[Проекты и системы сборки](projects-and-build-systems-cpp.md)<br/>
[Параметры компилятора MSVC](reference/compiler-options.md)
