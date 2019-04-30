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
ms.openlocfilehash: b4f941baae9f03ed288a99d59e2b06262962e339
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348748"
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