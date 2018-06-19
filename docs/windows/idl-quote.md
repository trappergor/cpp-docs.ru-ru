---
title: idl_quote | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_quote
dev_langs:
- C++
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8844a4770d0a4746c9d9de32a593d0770dcc9a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878516"
---
# <a name="idlquote"></a>idl_quote
Позволяет использовать IDL конструкции, которые не поддерживаются в текущей версии Visual C++ и их передачи через созданного IDL-файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### <a name="parameters"></a>Параметры  
 *текст*  
 Имя атрибута, который планируется компилятор Visual C++ для пропуска созданного IDL-файла, не возвращая ошибку компилятора.  
  
## <a name="remarks"></a>Примечания  
 Если **idl_quote** C++ используется в качестве изолированного атрибута (точку с запятой после закрывающей скобкой), затем *текст* помещается в объединенного IDL-файл как есть. Если **idl_quote** используется символ, *текст* помещается в блоке атрибутов для этого символа.  
  
## <a name="example"></a>Пример  
 В следующем коде показано, как можно указать неподдерживаемый атрибут (с помощью **в**, который поддерживается), а также для определения и использования конструкцией не определено .idl:  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Этот код вызывает MYFLOT и MYDUB и *текст* входа должно быть помещено в сгенерированный IDL-файл. *Имя* параметр заставляет *текст* должен располагаться перед все связанные *имя* в сгенерированный IDL-файл. *Зависимости* параметр предписывает определения список зависимостей, чтобы поместить перед *текст* в сгенерированный IDL-файл.  
  
## <a name="requirements"></a>Требования  
  
### <a name="attribute-context"></a>Контекст атрибута  
  
|||  
|-|-|  
|**Применение**|В любом месте|  
|**Повторяемый**|Нет|  
|**Обязательные атрибуты**|Нет|  
|**Недопустимые атрибуты**|Нет|  
  
 Дополнительные сведения см. в разделе [Контексты атрибутов](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>См. также  
 [Атрибуты IDL](../windows/idl-attributes.md)   
 [Изолированные атрибуты](../windows/stand-alone-attributes.md)   
