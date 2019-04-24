---
title: __wbinvd
ms.date: 11/04/2016
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: 99c7a452e063dea328e4aa1362aae8783929deb0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039271"
---
# <a name="wbinvd"></a>__wbinvd

**Блок, относящийся только к системам Microsoft**

Создает режим обратной записи и сделать недействительным кэш (`wbinvd`) инструкции.

## <a name="syntax"></a>Синтаксис

```
void __wbinvd(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__wbinvd`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта функция доступна только в режиме ядра с уровнем привилегий (CPL) 0 и процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)