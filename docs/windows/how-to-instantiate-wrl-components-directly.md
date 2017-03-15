---
title: "Практическое руководство. Непосредственное создание экземпляра компонентов WRL | Microsoft Docs"
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
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Практическое руководство. Непосредственное создание экземпляра компонентов WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сведения об использовании функций [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) [Microsoft::WRL::Make](../windows/make-function.md) и [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) для создания экземпляра компонента из определяющего его модуля.  
  
 С помощью создания компонентов напрямую можно уменьшить нагрузку, когда нет необходимости использовать фабрики классов или другие механизмы.  Можно создать компонент непосредственно в приложениях [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] и в классических приложениях.  
  
 Дополнительные сведения о том, как использовать [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] для создания базового компонента [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] и создать его экземпляр из внешнего приложения [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] см. в разделе [Пошаговое руководство. Создание базового компонента среды выполнения Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  Дополнительные сведения о том, как использовать [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] для создания компонента классической модели COM и создать его экземпляр из внешнего приложения, см. в разделе [Практическое руководство. Создание классического компонента COM](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 В этом документе показано два примера.  В первом примере используется функция `Make` для создания компонента.  Во втором примере используется функция `MakeAndInitialize` для создания компонента, который может создать ошибку во время построения. \(Поскольку модель COM обычно использует значения `HRESULT` вместо исключений, чтобы показать ошибки, тип модели COM обычно не вызывается из его конструктора.  `MakeAndInitialize` позволяет компоненту проверить его аргументы построения с помощью метода `RuntimeClassInitialize`\). Оба примера определяют базовый интерфейс ведения журнала и реализуют этот интерфейс, определяя класс, который выводит сообщения в консоль.  
  
> [!IMPORTANT]
>  Нельзя использовать оператор `new` для создания компонентов [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  Поэтому рекомендуется всегда использовать `Make` или `MakeAndInitialize`, чтобы создать компонент напрямую.  
  
### Создание базового компонента средства ведения журнала и его экземпляров  
  
1.  Создайте проект **Win32 Консольное приложение** в Visual Studio.  Назовите проект, например, `WRLLogger`.  
  
2.  Добавьте в проект файл **Midl файл \(.idl\)**, присвойте файлу имя `ILogger.idl`, а затем добавьте следующий код:  
  
     [!CODE [wrl-logger-make#1](../CodeSnippet/VS_Snippets_Misc/wrl-logger-make#1)]  
  
3.  Используйте следующий код, чтобы заменить содержимое WRLLogger.cpp.  
  
     [!CODE [wrl-logger-make#2](../CodeSnippet/VS_Snippets_Misc/wrl-logger-make#2)]  
  
### Обработка сбоя построения для базового компонента средства ведения журнала  
  
1.  Используйте следующий код, чтобы заменить определение класса `CConsoleWriter`.  Эта версия содержит закрытую строковую переменную\-член и переопределяет метод `RuntimeClass::RuntimeClassInitialize`.  `RuntimeClassInitialize` завершается неудачей, если вызов `SHStrDup` завершается неудачей.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.cpp)]  
  
2.  Используйте следующий код, чтобы заменить определение `wmain`.  Эта версия использует `MakeAndInitialize` для создания экземпляра объекта `CConsoleWriter` и проверяет результат `HRESULT`.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
## См. также  
 [Библиотека шаблонов C\+\+ среды выполнения Windows \(WRL\)](../Topic/Windows%20Runtime%20C++%20Template%20Library%20\(WRL\).md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)