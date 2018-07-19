---
title: Работа с потоками (C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f21ea8c16b4e09a5ad1845a10797be00f91b0d8f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891328"
---
# <a name="threading-c"></a>threading (C++)
Указывает, что потоковая модель для COM-объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 ***модель*** (необязательно)  
 Одно из следующих потоковые модели:  
  
-   **подразделения** (потоковое)  
  
-   **нейтральный** (компоненты .NET Framework без интерфейса пользователя)  
  
-   **один** (Работа с потоками в простой)  
  
-   **Бесплатные** (освобождения потоков)  
  
-   **оба** (подразделения и свободной потоковой модели)  
  
 Значение по умолчанию — **подразделения**.  
  
## <a name="remarks"></a>Примечания  
 **Работа с потоками** C++ атрибут не отображается в сгенерированный IDL-файл, но будет использоваться в реализации COM-объекта.  
  
 В проекты ATL Если [coclass](../windows/coclass.md) присутствует также атрибут, потоковой модели, указанный *модель* передается как параметр шаблона [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) класса , вставленное методом **coclass** атрибута.  
  
 **Работа с потоками** атрибута также защищает доступ к [event_source](../windows/event-source.md).  
  
## <a name="example"></a>Пример  
 В разделе [лицензированных](../windows/licensed.md) пример приведен пример использования **работа с потоками**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|**coclass**|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты COM](../windows/com-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Поддержка многопоточности для устаревшего кода (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [Нейтральный подразделения](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
