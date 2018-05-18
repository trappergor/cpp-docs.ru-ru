---
title: UUID (атрибуты C++) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e56793855b278e0631c39ebfcdc51669a001a24b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="uuid-c-attributes"></a>uuid (атрибуты C++)
Указывает уникальный идентификатор для класса или интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *uuid*  
 128 бит, уникальный идентификатор.  
  
## <a name="remarks"></a>Примечания  
 Если не указать определение класса или интерфейса `uuid` языка c++, то компилятор Visual C++ выдает один. При указании `uuid`, необходимо указывать в кавычках.  
  
 Если вы не укажете `uuid`, то компилятор создаст одинаковый идентификатор GUID для интерфейсов или классов с тем же именем в другой атрибут проекты на компьютере.  
  
 Uuidgen.exe или Guidgen.exe можно использовать для создания собственных уникальных идентификаторов. (Для запуска этих средств нажмите **запустить** и нажмите кнопку **запуска** меню. Затем введите имя средства требуется.)  
  
 При использовании в проекте, также не используйте ATL, указав `uuid` атрибут является тот же [uuid](../cpp/uuid-cpp.md) __declspec-модификатор. Для получения `uuid` класса, можно использовать [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>Пример  
 В разделе [привязываемых](../windows/bindable.md) пример приведен пример использования `uuid`.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**Класс**, `struct`, `interface`, **объединение**, `enum`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
