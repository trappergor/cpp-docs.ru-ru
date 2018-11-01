---
title: Практическое руководство. Получение указателя на массив байтов
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
ms.openlocfilehash: ad17dd0049f83fd753af0f9d7a565f28c6681a59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638906"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>Практическое руководство. Получение указателя на массив байтов

Вы можете получить указатель на блок массива в <xref:System.Byte> массива адрес первого элемента и присвоить его указателю.

## <a name="example"></a>Пример

```
// pointer_to_Byte_array.cpp
// compile with: /clr
using namespace System;
int main() {
   Byte bArr[] = {1, 2, 3};
   Byte* pbArr = &bArr[0];

   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};
   interior_ptr<Byte> pbArr2 = &bArr2[0];
}
```

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)