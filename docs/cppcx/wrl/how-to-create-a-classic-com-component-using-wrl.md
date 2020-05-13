---
title: Практическое руководство. Создание классического компонента COM с помощью WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: a1507a1a980dfd98a235b7456d73add955c02043
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213919"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Практическое руководство. Создание классического компонента COM с помощью WRL

Вы можете использовать библиотеку шаблонов C++ среда выполнения Windows (WRL) для создания базовых COM-компонентов, которые будут использоваться в классических приложениях, а также для приложений универсальная платформа Windows (UWP). Для создания COM-компонентов библиотека шаблонов среда выполнения Windows C++ может потребовать меньшего объема кода, чем ATL. Сведения о подмножестве COM, которое поддерживает библиотека C++ шаблонов среда выполнения Windows, см. в разделе [Библиотека шаблонов среда выполнения Windows C++ (WRL)](windows-runtime-cpp-template-library-wrl.md).

В этом документе показано, как использовать библиотеку C++ шаблонов среда выполнения Windows для создания базового COM-компонента. Хотя можно использовать механизм развертывания, который наилучшим образом соответствует требованиям, в этом документе также показан простой способ регистрации и использования компонента модели COM из обычного приложения для настольных систем.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Использование библиотеки шаблонов среда выполнения Windows C++ для создания базового COM-компонента

1. В Visual Studio создайте пустой проект **решения** . Присвойте проекту имя, например `WRLClassicCOM`.

2. Добавьте в решение **проект Win32** . Присвойте проекту имя, например `CalculatorComponent`. На вкладке **Параметры приложения** выберите **DLL**.

3. Добавьте в проект файл **MIDL (. IDL)** . Присвойте файлу имя, например `CalculatorComponent.idl`.

4. Добавьте этот код в файл CalculatorComponent.idl:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. В файле CalculatorComponent.cpp определите класс `CalculatorComponent`. Класс `CalculatorComponent` наследует от [Microsoft:: WRL:: RuntimeClass](runtimeclass-class.md). [Microsoft:: WRL:: RuntimeClassFlags\<классикком >](runtimeclassflags-structure.md) указывает, что класс является производным от [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) , а не [IInspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable). (`IInspectable` доступен только для среда выполнения Windows компонентов приложения.) `CoCreatableClass` создает фабрику для класса, который можно использовать с такими функциями, как [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Используйте следующий код, чтобы заменить код в `dllmain.cpp`. Этот файл определяет функции экспорта библиотек DLL. Эти функции используют класс [Microsoft:: WRL:: module](module-class.md) для управления фабриками классов для модуля.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Добавьте файл **определения модуля (DEF)** в проект. Присвойте файлу имя, например `CalculatorComponent.def`. Этот файл передает компоновщику имена функций, подлежащих экспорту.

8. Добавьте в файл CalculatorComponent.def следующий код:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Добавьте файл runtimeobject.lib в строку компоновщика. Дополнительные сведения см. в разделе [. Lib Files в качестве входных файлов компоновщика](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Использование компонента модели COM в обычном приложении для настольных систем

1. Зарегистрируйте компонент модели COM в реестре Windows. Для этого создайте файл регистрационных записей, назовите его `RegScript.reg`и добавьте следующий текст. Замените *\<DLL-path >* путем к библиотеке DLL, например `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`.

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. Запустите Регскрипт. reg или добавьте его в **событие после сборки**проекта. Дополнительные сведения см. в разделе [диалоговое окно "Командная строка события перед сборкой события/после сборки"](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Добавьте в решение проект **консольного приложения Win32** . Присвойте проекту имя, например `Calculator`.

4. Используйте этот код, чтобы заменить содержимое `Calculator.cpp`:

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Надежное программирование

В этом документе используются стандартные функции COM для демонстрации того, что можно использовать C++ библиотеку шаблонов среда выполнения Windows для создания компонента COM и сделать его доступным для любой технологии, поддерживающей COM. Вы также можете использовать среда выполнения Windows C++ типы библиотек шаблонов, например [Microsoft:: WRL:: ComPtr](comptr-class.md) , в классическом приложении для управления временем существования com и других объектов. В следующем коде используется библиотека шаблонов C++ среда выполнения Windows для управления временем существования указателя `ICalculatorComponent`. Класс `CoInitializeWrapper` является программой-оболочкой RAII, которая гарантирует, что библиотека COM освобождена и время ее жизни превысит время жизни объекта интеллектуального указателя `ComPtr`.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>См. также раздел

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)
