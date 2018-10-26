---
title: make_public | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eeabbfac65e67e0a293f4c31ff6f8911cc0b676e
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066725"
---
# <a name="makepublic"></a>make_public
Указывает, что собственный тип должен иметь открытый доступ к сборке.

## <a name="syntax"></a>Синтаксис

```
#pragma make_public(type)
```

### <a name="parameters"></a>Параметры

*Тип* — это имя типа, который вы хотите иметь открытый доступ к сборке.

## <a name="remarks"></a>Примечания

**make_public** полезно, когда собственный тип, если нужно сослаться, находится из файла .h, который нельзя изменить. Если требуется использовать собственный тип в сигнатуре открытой функции в типе с открытой видимостью сборки, собственный тип также должен иметь открытый доступ к сборке; в противном случае компилятор выдаст предупреждение.

**make_public** должен быть указан в глобальной области видимости и работает, только с момента его объявления и до конца файла исходного кода.

Собственный тип может быть неявно или явно закрытым; см. в разделе [видимость типов](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) Дополнительные сведения.

## <a name="examples"></a>Примеры

В следующем примере представлено содержимое файла .h, который содержит определения для двух собственных структур.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

В следующем образце кода используется файл заголовка и показывает, что если не задан явно как открытые, собственные структуры с помощью **make_public**, компилятор выдаст предупреждение при попытке использовать собственные структуры в сигнатуре открытой функции в открытом управляемом типе.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)