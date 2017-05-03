---
title: "Перевод типов и членов в разряд нерекомендуемых (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Перевод типов и членов в разряд нерекомендуемых (C++/CX)
В C\+\+\/CX поддерживается перевод типов и членов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] в состояние нерекомендуемых для производителей и получателей с помощью атрибута [Deprecated](http://msdn.microsoft.com/ru-ru/8b02ad36-3b5f-4361-888b-e6a99040e57c). При использовании элемента API, к которому был применен этот атрибут, вы получите предупреждение времени компиляции, в котором указывается, что данный элемент является нерекомендуемым и предлагается альтернатива. В собственных открытых типах и методах вы можете применять этот атрибут с заданием своего сообщения.  
  
> [!CAUTION]
>  Атрибут [Deprecated](http://msdn.microsoft.com/ru-ru/8b02ad36-3b5f-4361-888b-e6a99040e57c) может использоваться только с типами [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Для стандартных классов и членов C\+\+ используйте [\_\_declspec\(deprecated\)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
## Пример  
 В следующем примере показано, как переводить в число нерекомендуемых собственные открытые API, например в компоненте среды выполнения Windows. Второй параметр, имеющий тип [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/ru-ru/ee01e63d-37d0-4273-accc-fca174f88bfa), определяет, переводится элемент API в число нерекомендуемых или удаляется. В настоящее время поддерживается только значение DeprecationType::Deprecated. Третий параметр в атрибуте определяет платформу [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/ru-ru/1eae292d-1ab7-4d97-a58c-b0beffd51ef5), к которой применяется атрибут.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata; public ref class Bicycle sealed { public: property double Speed; [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)] double ComputeAngularVelocity(); };  
```  
  
## Поддерживаемые целевые объекты  
 В следующей таблице перечислены конструкции, к которым может применяться атрибут Deprecated:  
  
||  
|-|  
|элемент управления XAML|  
|делегат|  
|событие|  
|поле перечисления|  
|перечисление|  
|структура|  
|метод|  
|класс|  
|интерфейс|  
|свойство;|  
|поле структуры|  
|параметризованный конструктор|  
  
## См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)