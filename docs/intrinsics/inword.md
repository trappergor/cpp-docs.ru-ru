---
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: cfb6e5a11bed5feec3435ab604d22b8f532d3400
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217528"
---
# <a name="__inword"></a>__inword

**Блок, относящийся только к системам Microsoft**

Считывает данные из указанного порта с помощью `in` инструкции.

## <a name="syntax"></a>Синтаксис

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>Параметры

*Порту*\
окне Порт, из которого производится чтение.

## <a name="return-value"></a>Возвращаемое значение

Слово прочитанных данных.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__inword`|x86, x64|

**Заголовочный файл** \<> Intrin. h

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)
