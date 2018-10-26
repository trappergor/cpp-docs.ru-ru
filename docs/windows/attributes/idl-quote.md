---
title: idl_quote (атрибут COM C++) | Документация Майкрософт
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 31e06d83ce64675b5b1e8ac9cbb865bfb3eff334
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074167"
---
# <a name="idlquote"></a>idl_quote

Позволяет использовать конструкции IDL, которые не поддерживаются в текущей версии Visual C++ и их передачи через созданного IDL-файла.

## <a name="syntax"></a>Синтаксис

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>Параметры

*текст*<br/>
Имя атрибута, который предполагается компилятор Visual C++ для передачи созданного IDL-файла, не возвращая ошибку компилятора.

## <a name="remarks"></a>Примечания

Если **idl_quote** C++ используется в качестве изолированного атрибута (точкой с запятой после закрывающей скобки), затем *текст* помещается в объединенного IDL-файл как есть. Если **idl_quote** используется символ, *текст* помещается в блоке атрибутов данного символа.

## <a name="example"></a>Пример

В следующем коде показано, как можно указать неподдерживаемый атрибут (с помощью **в**, которая поддерживается) и как определить и использовать конструкцию неопределенный .idl:

```cpp
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

Этот код приводит к `MYFLOT` и `MYDUB` и *текст* записи должно быть помещено в созданного IDL-файла. *Имя* силы параметр *текст* помещается прежде всего, на который ссылается на *имя* созданного IDL-файла. *Зависимости* параметр вынуждает определения списка зависимостей должны быть помещены перед *текст* созданного IDL-файла.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)