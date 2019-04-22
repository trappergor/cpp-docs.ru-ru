---
title: __readdr
ms.date: 11/04/2016
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 9d265fe75abaa7ad3cfd508613766cc3b600ee14
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025670"
---
# <a name="readdr"></a>__readdr

Считывает значение указанного отладки регистра.

## <a name="syntax"></a>Синтаксис

```
unsigned         __readdr(unsigned int DebugRegister);
unsigned __int64 __readdr(unsigned int DebugRegister);
```

#### <a name="parameters"></a>Параметры

*DebugRegister*<br/>
[in] Зарегистрируйте константой, от 0 до 7, определяет debug.

## <a name="return-value"></a>Возвращаемое значение

Значение регистра указанного отладки.

## <a name="remarks"></a>Примечания

Эти встроенные функции доступны только в режиме ядра, а процедуры доступны только как встроенные функции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readdr`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)