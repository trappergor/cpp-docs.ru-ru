---
title: __writeeflags
ms.date: 11/04/2016
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: 6679a3b16def3ed413c5cec2a4bb7d5fe5d732c8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030359"
---
# <a name="writeeflags"></a>__writeeflags

Записывает указанное значение в программу состояния и управления (EFLAGS) регистрации.

## <a name="syntax"></a>Синтаксис

```
void __writeeflags(unsigned Value);
void __writeeflags(unsigned __int64 Value);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Значение*|[in] Значение для записи в EFLAGS регистр. `Value` Равен 32 бита времени для 32-разрядной платформе и 64 бита времени для 64-разрядной платформе.|

## <a name="remarks"></a>Примечания

Эти процедуры доступны только как встроенные функции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)