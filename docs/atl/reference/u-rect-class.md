---
title: Класс _U_RECT
ms.date: 11/04/2016
f1_keywords:
- ATL::_U_RECT
- _U_RECT
- ATL._U_RECT
helpviewer_keywords:
- U_RECT class
- _U_RECT class
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
ms.openlocfilehash: 306092a00a1e119263f4563eea181d7d3ee2b4b2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326378"
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

|Имя|Описание:|
|----------|-----------------|
|[_U_RECT::_U_RECT](#_u_rect___u_rect)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
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

*Версия-кандидат*<br/>
Объект `RECT` ссылки.

*lpRect*<br/>
Объект `RECT` указатель.

### <a name="remarks"></a>Примечания

Аргумент для конструктора указатель хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
