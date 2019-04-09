---
title: __inbytestring
ms.date: 11/04/2016
f1_keywords:
- __inbytestring
- __inbytestring_cpp
helpviewer_keywords:
- rep insb instruction
- __inbytestring intrinsic
ms.assetid: fe549556-e7a3-4af3-8ebf-8a7dc3cb233b
ms.openlocfilehash: e515c6452d18ca022707fa2f9e36e2045523ccd5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038587"
---
# <a name="inbytestring"></a>__inbytestring

**Блок, относящийся только к системам Microsoft**

Считывает данные из указанного порта с помощью `rep insb` инструкции.

## <a name="syntax"></a>Синтаксис

```
void __inbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для чтения из.

*Буфер*<br/>
[out] Данные, считанные из порта записывается здесь.

*Количество*<br/>
[in] Число байтов данных для чтения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__inbytestring`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)