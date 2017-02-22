---
title: "Практическое руководство. Создание классического компонента COM с помощью WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Практическое руководство. Создание классического компонента COM с помощью WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]), чтобы создать базовые компоненты классической модели COM для использования как в обычных приложениях, так и в приложениях, распространяемых через [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)]. Чтобы создать компоненты модели COM, в [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] может потребоваться меньше кода, чем для библиотеки ATL. Дополнительные сведения о подмножестве COM, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] поддерживает, в разделе [среды выполнения C++ шаблон библиотеки Windows (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md).  
  
 Этот документ демонстрирует использование [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] для создания базового компонента модели COM. Хотя можно использовать механизм развертывания, который наилучшим образом соответствует требованиям, в этом документе также показан простой способ регистрации и использования компонента модели COM из обычного приложения для настольных систем.  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-to-create-a-basic-classic-com-component"></a>Использование [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] для создания базового компонента классической модели COM  
  
1.  В Visual Studio создайте **пустое решение** проекта. Имя проекта, например, `WRLClassicCOM`.  
  
2.  Добавление **Проект Win32** в решение. Имя проекта, например, `CalculatorComponent`. На **Параметры приложения** выберите **DLL**.  
  
3.  Добавление **Midl файл (.idl)** файл в проект. Имя файла, например, `CalculatorComponent.idl`.  
  
4.  Добавьте этот код в файл CalculatorComponent.idl:  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  В файле CalculatorComponent.cpp определите класс `CalculatorComponent`.  `CalculatorComponent` Класс наследует от [Microsoft::wrl:: runtimeclass](../windows/runtimeclass-class.md). [Microsoft::wrl:: runtimeclassflags \< значением ClassicCom>](../windows/runtimeclassflags-structure.md) Указывает, что класс является производным от [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) и не [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` доступен только для [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] компоненты приложения.) `CoCreatableClass` создает фабрику для класса, который можно использовать с функциями, например [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  Замените содержимое файла dllmain.cpp следующим кодом. Этот файл определяет функции экспорта библиотек DLL. Эти функции используют [Microsoft::wrl:: module](../windows/module-class.md) класса для управления фабриками класса модуля.  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  Добавление **файл определения модуля (DEF)** файл в проект. Имя файла, например, `CalculatorComponent.def`. Этот файл передает компоновщику имена функций, подлежащих экспорту.  
  
8.  Добавьте в файл CalculatorComponent.def следующий код:  
  
     [!CODE [wrl-classic-com-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#4)]  
  
9. Добавьте файл runtimeobject.lib в строку компоновщика. Чтобы узнать, в статье [. LIB-файл в качестве входных данных компоновщика](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Использование компонента модели COM в обычном приложении для настольных систем  
  
1.  Зарегистрируйте компонент модели COM в реестре Windows. Чтобы сделать это, создайте файл записей регистрации, назовите его `RegScript.reg`, и добавьте следующий текст. Замените *\< путь dll >* путь к DLL-Библиотека — например, `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
     [!CODE [wrl-classic-com-component#5](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#5)]  
  
2.  Запустите файл RegScript.reg или добавьте его в проект **событие после построения**. Дополнительные сведения см. в разделе [перед построением события и после сборки событий командной строки диалогового](../Topic/Pre-build%20Event-Post-build%20Event%20Command%20Line%20Dialog%20Box.md).  
  
3.  Добавление **Консольное приложение Win32** проекта в решение. Имя проекта, например, `Calculator`.  
  
4.  Замените содержимое файла Calculator.cpp следующим кодом:  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В этом документе используются стандартные функции модели COM для демонстрации использования [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)], чтобы создать компонент модели COM и сделать его доступным для любой технологии, поддерживающей эту модель. Можно также использовать [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] типы, такие как [Microsoft::wrl:: comptr](../windows/comptr-class.md) в свое приложение для управления временем жизни COM и других объектов. В следующем коде используется [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] для управления временем жизни указателя `ICalculatorComponent`. Класс `CoInitializeWrapper` является программой-оболочкой RAII, которая гарантирует, что библиотека COM освобождена и время ее жизни превысит время жизни объекта интеллектуального указателя `ComPtr`.  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Библиотека шаблонов C++ среды выполнения Windows (WRL)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)