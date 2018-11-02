---
title: __movsb
ms.date: 11/04/2016
f1_keywords:
- __movsb
helpviewer_keywords:
- movsb instruction
- rep movsb instruction
- __movsb intrinsic
ms.assetid: ba5469f6-f797-4cd2-bee8-74c7666c26d4
ms.openlocfilehash: 4b68eb4ca735274243db0c9ae006aa04be55355f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666938"
---
# <a name="movsb"></a>__movsb

**Блок, относящийся только к системам Microsoft**

Создает строку переместить (`rep movsb`) инструкции.

## <a name="syntax"></a>Синтаксис

```
void __movsb( 
   unsigned char* Destination, 
   unsigned const char* Source, 
   size_t Count 
);
```

#### <a name="parameters"></a>Параметры

*Назначение*<br/>
[out] Указатель на место назначения копирования.

*Источник*<br/>
[in] Указатель на источник копирования.

*Количество*<br/>
[in] Число байтов для копирования.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__movsb`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

В результате первый `Count` байт, на которые указывают `Source` копируются `Destination` строка.

Эта процедура доступна только как встроенная функция.

## <a name="example"></a>Пример

```
// movsb.cpp
// processor: x86, x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsb)

int main()
{
    unsigned char s1[100];
    unsigned char s2[100] = "A big black dog.";
    __movsb(s1, s2, 100);

    printf_s("%s %s", s1, s2);
}
```

```Output
A big black dog. A big black dog.
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)