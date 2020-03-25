---
title: idl_quote (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: 4b05da6d237d71e0cc645ad0f626f75ecd85c827
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168033"
---
# <a name="idl_quote"></a>idl_quote

Позволяет использовать конструкции IDL, которые не поддерживаются в текущей версии Visual C++ , и передают их в созданный IDL-файл.

## <a name="syntax"></a>Синтаксис

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>Параметры

*text*<br/>
Имя атрибута, которое компилятор Майкрософт C++ должен передать в созданный IDL-файл, не возвращая ошибку компилятора.

## <a name="remarks"></a>Remarks

Если атрибут **idl_quote** C++ используется в качестве изолированного атрибута (с точкой с запятой после закрывающей скобки), то *текст* помещается в Объединенный IDL-файл как есть. Если в символе используется **idl_quote** , *текст* помещается в блок атрибутов для этого символа.

## <a name="example"></a>Пример

В следующем коде показано, как можно указать неподдерживаемый атрибут (с помощью **in**, который поддерживается) и как определить и использовать неопределенную конструкцию IDL:

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

Этот код вызывает `MYFLOT` и `MYDUB`, а также *текстовую* запись, помещаемую в созданный IDL-файл. Параметр *Name* задает принудительное размещение *текста* перед любым именем, ссылающимся на *имя* в созданном IDL-файле. Параметр *Dependencies* заставляет определения списка зависимостей размещаться перед *текстом* в созданном IDL-файле.

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|В любом месте|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты IDL](idl-attributes.md)<br/>
[Изолированные атрибуты](stand-alone-attributes.md)
