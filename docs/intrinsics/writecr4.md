---
title: __writecr4
ms.date: 11/04/2016
f1_keywords:
- _writecr4
helpviewer_keywords:
- _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
ms.openlocfilehash: 37bdde20b6d0fe1079969677250ce59acedf51ec
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328647"
---
# <a name="writecr4"></a>__writecr4

**Блок, относящийся только к системам Microsoft**

Записывает значение `Data` CR4 регистр.

## <a name="syntax"></a>Синтаксис

```
void writecr4(
   unsigned __int64 Data
);
```

#### <a name="parameters"></a>Параметры

*Данные*<br/>
[in] Значение для записи в CR4 регистр.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writecr4`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)