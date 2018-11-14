---
title: __outdword
ms.date: 11/04/2016
f1_keywords:
- __outdword
helpviewer_keywords:
- out instruction
- outdword instruction
- __outdword intrinsic
ms.assetid: ed1e4994-a84b-4759-8bf9-cd48fb073f4d
ms.openlocfilehash: dd2192842e2122ebb65dcfba9f1f68ec5fc468d5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331234"
---
# <a name="outdword"></a>__outdword

**Блок, относящийся только к системам Microsoft**

Создает `out` инструкции для отправки двойное `Data` номера порта `Port`.

## <a name="syntax"></a>Синтаксис

```
void __outdword(
   unsigned short Port,
   unsigned long Data
);
```

#### <a name="parameters"></a>Параметры

*Порт*<br/>
[in] Порт для отправки данных.

*Данные*<br/>
[in] Двойное отправки.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__outdword`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)