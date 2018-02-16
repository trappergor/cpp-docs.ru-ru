---
title: "Перевод типов и членов в разряд нерекомендуемых (C + +/ CX) | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1062a507d6281e003d9294de1c1cb39b7c01f9e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="deprecating-types-and-members-ccx"></a>Перевод типов и членов в разряд нерекомендуемых (C++/CX)
В C + +/ CX, не рекомендуется к использованию типов среды выполнения Windows и члены для производителей и получателей с помощью [Deprecated](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) атрибут поддерживается. При использовании элемента API, к которому был применен этот атрибут, вы получите предупреждение времени компиляции, в котором указывается, что данный элемент является нерекомендуемым и предлагается альтернатива. В собственных открытых типах и методах вы можете применять этот атрибут с заданием своего сообщения.  
  
> [!CAUTION]
>  [Deprecated](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) атрибут предназначен для использования только с типами среды выполнения Windows. Для стандартных классов и членов C++ используйте [__declspec(deprecated)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
### <a name="example"></a>Пример  
 В следующем примере показано, как переводить в число нерекомендуемых собственные открытые API, например в компоненте среды выполнения Windows. Второй параметр, имеющий тип [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/en-us/ee01e63d-37d0-4273-accc-fca174f88bfa) , определяет, переводится элемент API в число нерекомендуемых или удаляется. В настоящее время поддерживается только значение DeprecationType::Deprecated. Третий параметр в атрибуте определяет платформу [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/en-us/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) , к которой применяется атрибут.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata;  
  
public ref class Bicycle sealed  
{  
  
public:  
    property double Speed;  
  
    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]  
    double ComputeAngularVelocity();  
};  
```  
  
## <a name="supported-targets"></a>Поддерживаемые целевые объекты  
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
  
## <a name="see-also"></a>См. также  
 [Система типов](../cppcx/type-system-c-cx.md)   
 [Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)