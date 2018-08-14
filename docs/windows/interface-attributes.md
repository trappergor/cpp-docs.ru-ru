---
title: Атрибуты интерфейса | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f57cdce20a54b8bc56b804e12f59f92855c7f69
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880209"
---
# <a name="interface-attributes"></a>Атрибуты интерфейса
Следующие атрибуты, относящиеся к [interface (или __interface)](../cpp/interface.md) C++ ключевое слово.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|[async_uuid](../windows/async-uuid.md)|Указывает идентификатор UUID, компилятор MIDL для определения синхронные и асинхронные версии COM-интерфейса.|  
|[Настройка](../windows/custom-cpp.md)|Можно определить собственные атрибуты.|  
|[dispinterface](../windows/dispinterface.md)|Помещает интерфейс в IDL-файл в качестве интерфейса диспетчеризации.|  
|[dual](../windows/dual.md)|Помещает интерфейс в IDL-файл как сдвоенный интерфейс.|  
|[export](../windows/export.md)|В результате структуру данных помещается в IDL-файл.|  
|[helpcontext](../windows/helpcontext.md)|Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом элементе в файле справки.|  
|[helpfile](../windows/helpfile.md)|Задает имя файла справки для библиотеки типов.|  
|[helpstring](../windows/helpstring.md)|Определяет строку символов, используемый для описания элемента, к которому он применяется.|  
|[helpstringcontext](../windows/helpstringcontext.md)|Указывает идентификатор раздела справки в .hlp или CHM-файле.|  
|[helpstringdll](../windows/helpstringdll.md)|Указывает имя библиотеки DLL, в которых будет производиться выполняют поиск строки в документе (локализации).|  
|[hidden](../windows/hidden.md)|Указывает, что элемент существует, но не должен отображаться в пользовательском браузере.|  
|[library_block](../windows/library-block.md)|Помещает конструкцию внутри блока библиотеки IDL-файл.|  
|[Локальные](../windows/local-cpp.md)|Позволяет использовать компилятор MIDL как генератор заголовок при использовании в заголовке интерфейса. При использовании в отдельную функцию, назначает локальной процедуры, для которого заглушки не создаются.|  
|[nonextensible](../windows/nonextensible.md)|Указывает, что `IDispatch` реализация содержит только свойства и методы, перечисленных в описании интерфейса и не могут быть расширены с помощью дополнительных членов во время выполнения. Этот атрибут действителен только на [двойного](../windows/dual.md) интерфейса.|  
|[odl](../windows/odl.md)|Определяет интерфейс как интерфейс языка описания объектов (ODL).|  
|[object](../windows/object-cpp.md)|Определяет пользовательский интерфейс.|  
|[oleautomation](../windows/oleautomation.md)|Указывает, что интерфейс совместим с автоматизацией.|  
|[pointer_default](../windows/pointer-default.md)|Указывает атрибут указатель по умолчанию для всех указателей, за исключением указателей верхнего уровня, которые отображаются в списках параметров.|  
|[ptr](../windows/ptr.md)|Определяет указатель как полный указатель.|  
|[restricted](../windows/restricted.md)|Определяет, какие члены библиотеки не может вызываться произвольным образом.|  
|[uuid](../windows/uuid-cpp-attributes.md)|Предоставляет уникальный идентификатор библиотеки|  
  
 Должны соблюдаться следующие правила для определения интерфейса.  
  
-   Соглашение о вызовах по умолчанию — [__stdcall](../cpp/stdcall.md).  
  
-   Идентификатор GUID предоставляется для вас, если можно не указывать.  
  
-   Перегруженные методы не допускаются.  
  
 Если не указать [uuid](../windows/uuid-cpp-attributes.md) атрибута и с использованием имени интерфейса в проектах другой атрибут, создается одинаковый идентификатор GUID.  
  
## <a name="see-also"></a>См. также  
 [Список атрибутов по использованию](../windows/attributes-by-usage.md)