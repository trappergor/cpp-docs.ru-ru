---
title: vi_progid | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.vi_progid
dev_langs:
- C++
helpviewer_keywords:
- vi_progid attribute
ms.assetid: a52449be-b93e-4111-b883-44bb8da53261
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 687a8a70d7f0a5381160a6515c80f6940cc0a434
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="viprogid"></a>vi_progid
Указывает форму независимый от версии идентификатор ProgID.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ vi_progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Параметры  
 *name*  
 Независимый от версии идентификатор ProgID представляет объект.  
  
 Идентификаторы ProgID предоставляют более удобной для чтения версии идентификатор класса (CLSID), используемый для идентификации объектов COM и ActiveX.  
  
## <a name="remarks"></a>Примечания  
 **Vi_progid** языка c++ позволяет задать независимый от версии идентификатор ProgID для COM-объекта. Идентификатор ProgID имеет форму *name1.name2.version*. Независимый от версии идентификатор ProgID не имеет *версии*. Можно указать оба **progid** и **vi_progid** атрибуты компонентного класса. Если вы не укажете **vi_progid**, независимый от версии идентификатор ProgID — значения, указанного в [progid](../windows/progid.md) атрибута.  
  
 **vi_progid** подразумевает **coclass** атрибута, то есть, при указании **vi_progid**, это то же самое, что и при указании **coclass** и **vi_progid** атрибуты.  
  
 **Vi_progid** атрибут заставляет класс автоматически регистрироваться под указанным именем. Сгенерированный IDL-файл не будет отображать ProgID значение.  
  
 В проекты ATL Если [coclass](../windows/coclass.md) присутствует также атрибут, используемый указанным идентификатором ProgID **GetVersionIndependentProgID** функции (вставленным **компонентного класса** атрибут).  
  
## <a name="example"></a>Пример  
 В разделе [coclass](../windows/coclass.md) пример приведен пример использования **vi_progid**.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|**class**, `struct`|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union и Struct атрибуты](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Атрибуты классов](../windows/class-attributes.md)   
 [Идентификатор progID ключ](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
