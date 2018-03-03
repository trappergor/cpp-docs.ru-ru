---
title: "UUID (атрибуты C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba35dc89ae2567a499d4623f0c74293d2dbdcca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 *UUID*  
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
|**Применение**|**Класс**, `struct`, `interface`, **объединение**,`enum`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Атрибуты интерфейса](../windows/interface-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [UUID](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
