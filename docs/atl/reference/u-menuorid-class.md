---
title: Класс _U_MENUorID
ms.date: 11/04/2016
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
ms.openlocfilehash: 9388ca1751ee27fb25d6751c961d23e5243f2918
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495131"
---
# <a name="_u_menuorid-class"></a>Класс _U_MENUorID

Этот класс предоставляет оболочки для `CreateWindow` и. `CreateWindowEx`

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class _U_MENUorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Маркер меню.|

## <a name="remarks"></a>Примечания

Этот класс адаптера Argument позволяет передавать в функцию идентификаторы (UINT) или дескрипторы меню (Хменус) без необходимости явного приведения в части вызывающего объекта.

Этот класс предназначен для реализации оболочек для API Windows, в частности функций [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) и [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw) , которые принимают аргумент HMENU, который может быть идентификатором дочернего окна (UINT), а не маркером меню. Например, можно увидеть, что этот класс используется в качестве параметра для [квиндовимпл:: Create](cwindowimpl-class.md#create).

Класс определяет две перегрузки конструктора: одна принимает аргумент UINT, а другая принимает аргумент HMENU. Аргумент UINT просто приведен к HMENU в конструкторе и результату, хранящемуся в одном элементе данных класса, [m_hMenu](#_u_menuorid__m_hmenu). Аргумент для конструктора HMENU хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin. h

##  <a name="_u_menuorid__m_hmenu"></a>_U_MENUorID::m_hMenu

Класс содержит значение, передаваемое в любой из его конструкторов как открытый элемент данных HMENU.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>_U_MENUorID::_U_MENUorID

Аргумент UINT просто приведен к HMENU в конструкторе и результату, хранящемуся в одном элементе данных класса, [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор дочернего окна.

*hMenu*<br/>
Маркер меню.

### <a name="remarks"></a>Примечания

Аргумент для конструктора HMENU хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Обзор класса](../../atl/atl-class-overview.md)
