---
title: Практическое руководство. Создание классического компонента COM с использованием WRL
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: bb38f36cdd481e61d049f82159fdc24c3726f646
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031846"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Практическое руководство. Создание классического компонента COM с использованием WRL

Windows шаблонов среды выполнения C++ Library (WRL) можно использовать для создания основных классических компонентов COM для использования в классических приложениях, только для приложений универсальной платформы Windows (UWP). Для создания COM-компонентов библиотека шаблонов C++ среды выполнения Windows может потребоваться меньше кода, чем для библиотеки ATL. Дополнительные сведения о подмножестве модели COM, который поддерживает библиотека шаблонов C++ среды выполнения Windows, см. в разделе [библиотеки шаблонов C++ (WRL) среды выполнения Windows](windows-runtime-cpp-template-library-wrl.md).

В этом документе показано, как использовать библиотека шаблонов C++ среды выполнения Windows для создания базового COM-компонента. Хотя можно использовать механизм развертывания, который наилучшим образом соответствует требованиям, в этом документе также показан простой способ регистрации и использования компонента модели COM из обычного приложения для настольных систем.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Использовать библиотека шаблонов C++ среды выполнения Windows для создания базового компонента классической модели COM

1. В Visual Studio создайте **пустое решение** проекта. Например, назовите проект, `WRLClassicCOM`.

2. Добавить **проект Win32** в решение. Например, назовите проект, `CalculatorComponent`. На **параметры приложения** выберите **DLL**.

3. Добавить **файл Midl (.idl)** файл в проект. Имя файла, например, `CalculatorComponent.idl`.

4. Добавьте этот код в файл CalculatorComponent.idl:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. В файле CalculatorComponent.cpp определите класс `CalculatorComponent`. `CalculatorComponent` Класс наследует от [Microsoft::wrl:: runtimeclass](runtimeclass-class.md). [Microsoft::wrl:: runtimeclassflags\<ClassicCom >](runtimeclassflags-structure.md) указывает, что класс является производным от [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) и не [IInspectable](/windows/desktop/api/inspectable/nn-inspectable-iinspectable). (`IInspectable` доступен только для компонентов приложения среды выполнения Windows.) `CoCreatableClass` создает фабрику для класса, который можно использовать с помощью функции например [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance).

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Используйте указанный ниже код вместо кода в `dllmain.cpp`. Этот файл определяет функции экспорта библиотек DLL. Эти функции используют [Microsoft::wrl:: module](module-class.md) класса для управления фабриками класса модуля.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Добавить **файл определения модуля (.def)** файл в проект. Имя файла, например, `CalculatorComponent.def`. Этот файл передает компоновщику имена функций, подлежащих экспорту.

8. Добавьте в файл CalculatorComponent.def следующий код:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Добавьте файл runtimeobject.lib в строку компоновщика. Чтобы узнать как это сделать, см. в разделе [. LIB-файл в качестве входных данных компоновщика](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Использование компонента модели COM в обычном приложении для настольных систем

1. Зарегистрируйте компонент модели COM в реестре Windows. Чтобы сделать это, создайте файл записей регистрации, назовите его `RegScript.reg`и добавьте следующий текст. Замените  *\<dll-path >* с путь к библиотеке DLL — например, `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`.

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

2. Запустите файл RegScript.reg или добавьте его в проект **POST-Build Event**. Дополнительные сведения см. в разделе [перед сборкой события и после сборки событий командной строки диалоговое окно](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).

3. Добавить **консольное приложение Win32** проекта к решению. Например, назовите проект, `Calculator`.

4. Используйте этот код, чтобы заменить содержимое `Calculator.cpp`:

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Отказоустойчивость

В этом документе используется стандартных функций COM для демонстрации того, что библиотека шаблонов C++ среды выполнения Windows можно использовать для создания COM-компонент и сделает его доступным для любой технологии с поддержкой модели COM. Можно также использовать типы библиотека шаблонов C++ среды выполнения Windows например [Microsoft::wrl:: comptr](comptr-class.md) в Классические приложения для управления временем жизни COM и других объектов. В следующем коде используется библиотека шаблонов C++ среды выполнения Windows для управления временем жизни `ICalculatorComponent` указатель. Класс `CoInitializeWrapper` является программой-оболочкой RAII, которая гарантирует, что библиотека COM освобождена и время ее жизни превысит время жизни объекта интеллектуального указателя `ComPtr`.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>См. также

[Библиотека шаблонов C++ среды выполнения Windows (WRL)](windows-runtime-cpp-template-library-wrl.md)