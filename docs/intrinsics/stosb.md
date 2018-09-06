---
title: __stosb | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __stosb
dev_langs:
- C++
helpviewer_keywords:
- rep stosb instruction
- __stosb intrinsic
- stosb instruction
ms.assetid: 634589ed-2da3-439b-a381-a214d89bf10c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61050f8fc1924f6d2a143893af5bd1918df94394
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895192"
---
# <a name="stosb"></a>__stosb

**Блок, относящийся только к системам Microsoft**

Создает инструкцию строка магазина (`rep stosb`).

## <a name="syntax"></a>Синтаксис

```
void __stosb(
   unsigned char* Dest,
   unsigned char Data,
   size_t Count
);
```

#### <a name="parameters"></a>Параметры

[выходной] `Dest`  
Целевой для операции.

[in] `Data`  
Сохраняемые данные.

[in] `Count`  
Длина блока байтов для записи.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__stosb`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Результатом является то, что символ `Data` записывается в блок `Count` байтов в `Dest` строку.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```C
// stosb.c
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__stosb)  

int main()  
{
    unsigned char c = 0x40; /* '@' character */
    unsigned char s[] = "*********************************";

    printf_s("%s\n", s);
    __stosb((unsigned char*)s+1, c, 6);
    printf_s("%s\n", s);

}
```  

```Output
*********************************  
*@@@@@@**************************  
```  

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)