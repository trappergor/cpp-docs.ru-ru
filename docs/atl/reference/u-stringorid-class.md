---
title: Класс _U_STRINGorID
ms.date: 11/04/2016
f1_keywords:
- ATL._U_STRINGorID
- ATL::_U_STRINGorID
- _U_STRINGorID
helpviewer_keywords:
- _U_STRINGorID class
- U_STRINGorID class
ms.assetid: 443cdc00-d265-4b27-8ef3-2feb95f3e5e3
ms.openlocfilehash: c57d983e9680ce6d2cab375e427b80f4d3b6c2d6
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739578"
---
# <a name="_u_stringorid-class"></a>Класс _U_STRINGorID

Этот класс адаптера Argument позволяет передавать в функцию имена ресурсов (Лпктстрс) или идентификаторы ресурсов (UINT), не требуя от вызывающего объекта преобразования идентификатора в строку с помощью макроса МАКЕИНТРЕСАУРЦЕ.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class _U_STRINGorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Идентификатор ресурса.|

## <a name="remarks"></a>Примечания

Этот класс предназначен для реализации оболочек для API управления ресурсами Windows, таких как функции [FindResource](/windows/win32/api/winbase/nf-winbase-findresourcea), [лоадикон](/windows/win32/api/winuser/nf-winuser-loadiconw)и [ЛОАДМЕНУ](/windows/win32/api/winuser/nf-winuser-loadmenuw) , которые принимают аргумент LPCTSTR, который может быть либо именем ресурса, либо его идентификатором.

Класс определяет две перегрузки конструктора: одна принимает аргумент LPCTSTR, а другая принимает аргумент UINT. Аргумент UINT преобразуется в тип ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса МАКЕИНТРЕСАУРЦЕ и результата, хранящегося в единственном элементе данных класса [m_lpstr](#_u_stringorid__m_lpstr). Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

##  <a name="_u_stringorid__m_lpstr"></a>_U_STRINGorID::m_lpstr

Класс содержит значение, передаваемое в любой из его конструкторов как открытый элемент данных LPCTSTR.

```
LPCTSTR m_lpstr;
```

##  <a name="_u_stringorid___u_stringorid"></a>_U_STRINGorID::_U_STRINGorID

Конструктор UINT преобразует свой аргумент в тип ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса МАКЕИНТРЕСАУРЦЕ, а результат хранится в одном элементе данных класса, [m_lpstr](#_u_stringorid__m_lpstr).

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса.

*лпстринг*<br/>
Имя ресурса.

### <a name="remarks"></a>Примечания

Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
