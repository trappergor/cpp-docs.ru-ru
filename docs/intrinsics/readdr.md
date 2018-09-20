---
title: __readdr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readdr
dev_langs:
- C++
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dffb51782e87903feaeb733765fcf9f4763a64f6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385148"
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