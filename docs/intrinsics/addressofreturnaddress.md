---
title: _AddressOfReturnAddress
ms.date: 11/04/2016
f1_keywords:
- _AddressOfReturnAddress_cpp
- _AddressOfReturnAddress
helpviewer_keywords:
- _AddressOfReturnAddress intrinsic
- AddressOfReturnAddress intrinsic
ms.assetid: c7e10b8c-445e-4236-a602-e2d90200f70a
ms.openlocfilehash: 678128c4b09b083b4afe3a86c9b2315eb3c87b1b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584487"
---
# <a name="addressofreturnaddress"></a>_AddressOfReturnAddress

**Блок, относящийся только к системам Microsoft**

Предоставляет адрес области памяти, содержащий обратный адрес текущей функции. Этот адрес не может использоваться для доступа к другим расположениям памяти (например, аргументов функции).

## <a name="syntax"></a>Синтаксис

```
void * _AddressOfReturnAddress();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_AddressOfReturnAddress`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Когда `_AddressOfReturnAddress` используется в программы, скомпилированной с [/CLR](../build/reference/clr-common-language-runtime-compilation.md), функция, содержащая `_AddressOfReturnAddress` вызов скомпилирована как собственная функция. Если функция скомпилирована как управляемые вызовы в функцию, содержащую `_AddressOfReturnAddress`, `_AddressOfReturnAddress` может вести себя непредусмотренным образом.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// compiler_intrinsics_AddressOfReturnAddress.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

// This function will print three values:
//   (1) The address retrieved from _AddressOfReturnAdress
//   (2) The return address stored at the location returned in (1)
//   (3) The return address retrieved the _ReturnAddress* intrinsic
// Note that (2) and (3) should be the same address.
__declspec(noinline)
void func() {
   void* pvAddressOfReturnAddress = _AddressOfReturnAddress();
   printf_s("%p\n", pvAddressOfReturnAddress);
   printf_s("%p\n", *((void**) pvAddressOfReturnAddress));
   printf_s("%p\n", _ReturnAddress());
}

int main() {
   func();
}
```

```Output
0012FF78
00401058
00401058
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)