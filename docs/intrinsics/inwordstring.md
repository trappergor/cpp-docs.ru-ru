---
title: __inwordstring
ms.date: 11/04/2016
f1_keywords:
- __inwordstring
- __inwordstring_cpp
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
ms.openlocfilehash: 52c36754e1eea56b84eeb494e82e37a5b043246e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030223"
---
# <a name="inwordstring"></a>__inwordstring

**Блок, относящийся только к системам Microsoft**

Считывает данные из указанного порта с помощью `rep insw` инструкции.

## <a name="syntax"></a>Синтаксис

```
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для чтения из.

*Буфер*<br/>
[out] Данные, считанные из порта записывается здесь.

*Количество*<br/>
[in] Число слов в данных для чтения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__inwordstring`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)