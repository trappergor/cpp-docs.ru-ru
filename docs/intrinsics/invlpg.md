---
title: __invlpg
ms.date: 11/04/2016
f1_keywords:
- __invlpg
- __invlpg_cpp
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
ms.openlocfilehash: 0ff46aa15fbb8728ce02255209a32f01a168609b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629389"
---
# <a name="invlpg"></a>__invlpg

**Блок, относящийся только к системам Microsoft**

Создает x86 `invlpg` инструкции, что делает недействительным буфера ассоциативной трансляции (TLB) для страницы, связанные с объемом памяти, на которые указывают `Address`.

## <a name="syntax"></a>Синтаксис

```
void __invlpg(
   void* Address
);
```

#### <a name="parameters"></a>Параметры

*Адрес*<br/>
[in] 64-разрядный адрес.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__invlpg`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Встроенная `__invlpg` выдает привилегированной инструкции и доступна только в режиме ядра с уровнем привилегий (CPL) 0.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)