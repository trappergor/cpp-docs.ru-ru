---
title: __wbinvd
ms.date: 11/04/2016
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: 0f775ba94c2dee1c2568e66b09fa1ffb31f512bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482541"
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