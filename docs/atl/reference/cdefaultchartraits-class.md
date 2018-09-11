---
title: Класс CDefaultCharTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 080a7b9f5da71535f8b141555ec1890a521fe715
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761986"
---
# <a name="cdefaultchartraits-class"></a>Класс CDefaultCharTraits

Этот класс предоставляет два статических функций для преобразования символов в верхний или нижний регистр.

## <a name="syntax"></a>Синтаксис

```
template <typename T>  
class CDefaultCharTraits
```

#### <a name="parameters"></a>Параметры

*T*  
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultCharTraits::CharToLower](#chartolower)|(Статический) Вызывайте эту функцию для преобразования символа в верхний регистр.|
|[CDefaultCharTraits::CharToUpper](#chartoupper)|(Статический) Вызывайте эту функцию для преобразования символа в нижний регистр.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет функции, которые используются классом [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="chartolower"></a>  CDefaultCharTraits::CharToLower

Вызывайте эту функцию для преобразования символа в нижний регистр.

```
static wchar_t CharToLower(wchar_t x);  
static char CharToLower(char x);
```

### <a name="parameters"></a>Параметры

*x*  
Знак для преобразования в нижний регистр.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

##  <a name="chartoupper"></a>  CDefaultCharTraits::CharToUpper

Вызывайте эту функцию для преобразования символа в верхний регистр.

```
static wchar_t CharToUpper(wchar_t x);  
static char CharToUpper(char x);
```

### <a name="parameters"></a>Параметры

*x*  
Знак для преобразования в верхний регистр.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
