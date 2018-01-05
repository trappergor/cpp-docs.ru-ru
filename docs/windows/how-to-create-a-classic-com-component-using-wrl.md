---
title: "Как: создание классического компонента COM с использованием WRL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04b84a5deedc5ef112507f4e0f8ccb29af418c28
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Практическое руководство. Создание классического компонента COM с помощью WRL
Среда выполнения C++ шаблон библиотеки Windows (WRL) можно использовать для создания базовые компоненты классической модели COM для использования в классических приложениях, кроме через [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)] приложений. Для создания COM-компонентов библиотека шаблонов C++ среды выполнения Windows может потребоваться меньше кода, чем для библиотеки ATL. Дополнительные сведения о подмножестве модели COM, который поддерживает библиотека шаблонов C++ среды выполнения Windows, в разделе [библиотеки шаблонов C++ (WRL) среды выполнения Windows](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 В этом документе показано, как использовать библиотека шаблонов C++ среды выполнения Windows для создания базового COM-компонента. Хотя можно использовать механизм развертывания, который наилучшим образом соответствует требованиям, в этом документе также показан простой способ регистрации и использования компонента модели COM из обычного приложения для настольных систем.  
  
### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>Использование библиотека шаблонов C++ среды выполнения Windows для создания основных компонента COM  
  
1.  В Visual Studio создайте **пустое решение** проекта. Задайте имя проекта, например, `WRLClassicCOM`.  
  
2.  Добавить **проект Win32** в решение. Задайте имя проекта, например, `CalculatorComponent`. На **параметры приложения** выберите **DLL**.  
  
3.  Добавить **Midl файл (.idl)** файл в проект. Имя файла, например, `CalculatorComponent.idl`.  
  
4.  Добавьте этот код в файл CalculatorComponent.idl:  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  В файле CalculatorComponent.cpp определите класс `CalculatorComponent`. `CalculatorComponent` Класс наследует от [Microsoft::wrl:: runtimeclass](../windows/runtimeclass-class.md). [Microsoft::wrl:: runtimeclassflags\<ClassicCom >](../windows/runtimeclassflags-structure.md) указывает, что класс является производным от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) и не [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` доступен только для [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] компоненты приложения.) `CoCreatableClass` создает фабрику для класса, который можно использовать с функции например [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  Замените содержимое файла dllmain.cpp следующим кодом. Этот файл определяет функции экспорта библиотек DLL. Эти функции используют [Microsoft::wrl:: module](../windows/module-class.md) класса для управления фабриками класса модуля.  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  Добавить **файл определения модуля (DEF)** файл в проект. Имя файла, например, `CalculatorComponent.def`. Этот файл передает компоновщику имена функций, подлежащих экспорту.  
  
8.  Добавьте в файл CalculatorComponent.def следующий код:  
  
    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE  
    ```

9. Добавьте файл runtimeobject.lib в строку компоновщика. Дополнительные сведения см. в разделе [. LIB-файл в качестве входных данных компоновщика](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Использование компонента модели COM в обычном приложении для настольных систем  
  
1.  Зарегистрируйте компонент модели COM в реестре Windows. Чтобы сделать это, создайте файл записей регистрации, назовите его `RegScript.reg`и добавьте следующий текст. Замените  *\<dll-path >* с путь к библиотеке DLL — например, `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
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
  
2.  Запустите файл RegScript.reg или добавьте его в проект **события после построения**. Дополнительные сведения см. в разделе [перед построением события и после построения командной строки диалоговом события](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box).  
  
3.  Добавить **консольное приложение Win32** проекта в решение. Задайте имя проекта, например, `Calculator`.  
  
4.  Замените содержимое файла Calculator.cpp следующим кодом:  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом документе использует стандартные функции модели COM для демонстрации создания COM-компонента и сделать его доступным для любой технологии поддержкой модели COM используется библиотека шаблонов C++ среды выполнения Windows. Можно также использовать типы библиотека шаблонов C++ среды выполнения Windows например [Microsoft::wrl:: comptr](../windows/comptr-class.md) в приложении для настольных систем для управления временем жизни модели COM и других объектов. В следующем коде используется библиотека шаблонов C++ среды выполнения Windows для управления временем жизни `ICalculatorComponent` указателя. Класс `CoInitializeWrapper` является программой-оболочкой RAII, которая гарантирует, что библиотека COM освобождена и время ее жизни превысит время жизни объекта интеллектуального указателя `ComPtr`.  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)