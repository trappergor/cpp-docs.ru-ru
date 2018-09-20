---
title: Класс CD2DBrushProperties | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c02c2b2e6b0c24ab4f12d0d6b9c04927b2cba8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440554"
---
# <a name="cd2dbrushproperties-class"></a>Класс CD2DBrushProperties

Программа-оболочка для `D2D1_BRUSH_PROPERTIES`.

## <a name="syntax"></a>Синтаксис

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Перегружен. Создает `CD2D_BRUSH_PROPERTIES` структуры|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CD2DBrushProperties::CommonInit](#commoninit)|Инициализирует объект|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>Требования

**Заголовок:** afxrendertarget.h

##  <a name="cd2dbrushproperties"></a>  CD2DBrushProperties::CD2DBrushProperties

Создает структуру CD2D_BRUSH_PROPERTIES

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);


CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>Параметры

*_opacity*<br/>
Базовый непрозрачность кисти. Значение по умолчанию — 1,0.

*_transform*<br/>
Преобразование, применяемое к кисти

##  <a name="commoninit"></a>  CD2DBrushProperties::CommonInit

Инициализирует объект

```
void CommonInit();
```

## <a name="see-also"></a>См. также

[Классы](../../mfc/reference/mfc-classes.md)
