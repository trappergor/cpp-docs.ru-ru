---
title: __writedr
ms.date: 11/04/2016
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: c495e8c80029680512358198ca8fb0ce6e65414d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022485"
---
# <a name="writedr"></a>__writedr

Записывает заданное значение для регистрации указанного отладки.

## <a name="syntax"></a>Синтаксис

```
void __writedr(unsigned DebugRegister, unsigned DebugValue);
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);
```

#### <a name="parameters"></a>Параметры

*DebugRegister*<br/>
[in] Число от 0 до 7, определяет отладочные регистрации.

*DebugValue*<br/>
[in] Значение для записи отладочной регистрации.

## <a name="remarks"></a>Примечания

Эти встроенные функции доступны только в режиме ядра, а процедуры доступны только как встроенные функции.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writedr`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__readdr](../intrinsics/readdr.md)