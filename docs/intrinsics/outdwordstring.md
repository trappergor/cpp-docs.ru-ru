---
title: __outdwordstring
ms.date: 11/04/2016
f1_keywords:
- __outdwordstring
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
ms.openlocfilehash: 51cb4a97d271d6d41d39d1025e3a5d34b273cdc4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396591"
---
# <a name="outdwordstring"></a>__outdwordstring

**Блок, относящийся только к системам Microsoft**

Создает `rep outsd` инструкция, которая отправляет `Count` двойных слов, начиная с `Buffer` номера порта ввода-вывода, определяемое `Port`.

## <a name="syntax"></a>Синтаксис

```
void __outdwordstring(
   unsigned short Port,
   unsigned long* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для отправки данных.

*буфер*<br/>
[in] Указатель на данные, которые будут отправлены для указанного порта.

*Количество*<br/>
[in] Число двойных слов для отправки.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__outdwordstring`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)