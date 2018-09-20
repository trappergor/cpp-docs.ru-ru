---
title: auto_handle::operator bool | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- auto_handle.operator bool
- msclr.auto_handle.operator bool
- operator bool
- msclr::auto_handle::operator bool
- auto_handle::operator bool
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::operator bool
ms.assetid: 2e535e99-cf87-4008-b588-02c587d77453
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: be9c1bc8125c30eb2208b389097eac7e1cf38e09
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374390"
---
# <a name="autohandleoperator-bool"></a>auto_handle::operator bool

Оператор для использования `auto_handle` в условном выражении.

## <a name="syntax"></a>Синтаксис

```
operator bool();
```

## <a name="return-value"></a>Возвращаемое значение

`true` Если инкапсулированный объект является допустимым; `false` в противном случае.

## <a name="remarks"></a>Примечания

Этот оператор фактически преобразует `_detail_class::_safe_bool` которого является более безопасным, чем `bool` , так как он не может быть преобразован в целочисленный тип.

## <a name="example"></a>Пример

```
// msl_auto_handle_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1;
   auto_handle<String> s2 = "hi";
   if ( s1 ) Console::WriteLine( "s1 is valid" );
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );
   if ( s2 ) Console::WriteLine( "s2 is valid" );
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );
   s2.reset();
   if ( s2 ) Console::WriteLine( "s2 is now valid" );
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );
}
```

```Output
s1 is invalid
s2 is valid
s2 is now invalid
```

## <a name="requirements"></a>Требования

**Файл заголовка** \<msclr\auto_handle.h >

**Пространство имен** msclr

## <a name="see-also"></a>См. также

[Члены auto_handle](../dotnet/auto-handle-members.md)<br/>
[auto_handle::operator!](../dotnet/auto-handle-operator-logical-not.md)