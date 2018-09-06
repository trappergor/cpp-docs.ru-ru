---
title: Класс _U_RECT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
dev_langs:
- C++
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1041141e9f31e59ab7a1884e976828972c0abd91
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767328"
---
# <a name="urect-class"></a>Класс _U_RECT

Предоставляет класс адаптера этот аргумент `RECT` указатели или ссылки, должны быть переданы функции, которая реализуется в терминах указатели.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class _U_RECT
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_RECT::m_lpRect](#_u_rect__m_lprect)|Указатель на `RECT`.|

## <a name="remarks"></a>Примечания

Этот класс определяет две перегрузки конструктора: одна принимает **RECT &** аргумент, а другой принимает `LPRECT` аргумент. Первый конструктор сохраняет адрес ссылочный аргумент в единый данные-член класса, [m_lpRect](#_u_rect__m_lprect). Аргумент для конструктора указатель хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="_u_rect__m_lprect"></a>  _U_RECT::m_lpRect

Класс содержит значение, передаваемое в любой из его конструкторов как открытый `LPRECT` элемент данных.

```
LPRECT m_lpRect;
```

##  <a name="_u_rect___u_rect"></a>  _U_RECT::_U_RECT

Адрес ссылочный аргумент хранится в одном данные-член класса, [m_lpRect](#_u_rect__m_lprect).

```
_U_RECT(RECT& rc);  
_U_RECT(LPRECT lpRect);
```

### <a name="parameters"></a>Параметры

*Версия-кандидат*  
Объект `RECT` ссылки.

*lpRect*  
Объект `RECT` указатель.

### <a name="remarks"></a>Примечания

Аргумент для конструктора указатель хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
