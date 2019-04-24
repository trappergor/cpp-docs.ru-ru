---
title: __outbytestring
ms.date: 11/04/2016
f1_keywords:
- __outbytestring
helpviewer_keywords:
- rep outsb instruction
- __outbytestring intrinsic
- outsb instruction
ms.assetid: c9150661-9c18-427f-bae8-710bba6ed78c
ms.openlocfilehash: 41064dda6a1a0b9ad4c15f98c3f3081f08ef8db6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032197"
---
# <a name="outbytestring"></a>__outbytestring

**Блок, относящийся только к системам Microsoft**

Создает `rep outsb` инструкция, которая отправляет первый `Count` байтов данных, на которые указывают `Buffer` на порт, заданный `Port`.

## <a name="syntax"></a>Синтаксис

```
void __outbytestring(
   unsigned short Port,
   unsigned char* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для отправки данных.

*буфер*<br/>
[in] Данные будут отправлены для указанного порта.

*Количество*<br/>
[in] Число байтов данных для отправки.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__outbytestring`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)