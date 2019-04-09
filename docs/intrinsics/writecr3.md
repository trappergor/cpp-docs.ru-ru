---
title: __writecr3
ms.date: 11/04/2016
f1_keywords:
- _writecr3
helpviewer_keywords:
- _writecr3 intrinsic
ms.assetid: 959d49fa-69d5-47cf-88d2-7688367fe38f
ms.openlocfilehash: 88467e4fb39abc9526e47a73f998d630470111a9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037371"
---
# <a name="writecr3"></a>__writecr3

**Блок, относящийся только к системам Microsoft**

Записывает значение `Data` CR3 регистр.

## <a name="syntax"></a>Синтаксис

```
void writecr3(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Параметры

*Данные*<br/>
[in] Значение для записи в CR3 регистр.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writecr3`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)