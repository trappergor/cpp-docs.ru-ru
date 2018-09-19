---
title: Класс _U_MENUorID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL._U_MENUorID
- ATL::_U_MENUorID
- _U_MENUorID
dev_langs:
- C++
helpviewer_keywords:
- U_MENUorID class
- _U_MENUorID class
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e5902019704821d6c34c74480623593b7d7448a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044253"
---
# <a name="umenuorid-class"></a>Класс _U_MENUorID

Этот класс предоставляет оболочки для `CreateWindow` и `CreateWindowEx`.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class _U_MENUorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_MENUorID::_U_MENUorID](#_u_menuorid___u_menuorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_MENUorID::m_hMenu](#_u_menuorid__m_hmenu)|Дескриптор для меню.|

## <a name="remarks"></a>Примечания

Этот класс адаптера аргумент позволяет идентификаторы (единицы) или дескрипторы меню (HMENUs) для передачи в функцию без необходимости явного приведения, со стороны вызывающего объекта.

Этот класс предназначен для реализации оболочки Windows API, особенно [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) и [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) функции, которые принимают аргумент дескриптора HMENU, возможно, дочернее окно идентификатор (целое число без знака), а не дескриптор меню. Например, можно увидеть этот класс используется в качестве параметра [CWindowImpl::Create](cwindowimpl-class.md#create).  

Этот класс определяет две перегрузки конструктора: один принимает аргумент целое число без знака, а другой принимает аргумент дескриптора HMENU. Целое число без знака аргумент просто привести к HMENU конструктора и результата, хранимого в единый данные-член класса, [m_hMenu](#_u_menuorid__m_hmenu). Аргумент для конструктора HMENU хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="_u_menuorid__m_hmenu"></a>  _U_MENUorID::m_hMenu

Класс содержит значение, передаваемое в любой из его конструкторов как открытый элемент данных дескриптора HMENU.

```
HMENU m_hMenu;
```

##  <a name="_u_menuorid___u_menuorid"></a>  _U_MENUorID::_U_MENUorID

Целое число без знака аргумент просто привести к HMENU конструктора и результата, хранимого в единый данные-член класса, [m_hMenu](#_u_menuorid__m_hmenu).

```
_U_MENUorID(UINT nID);
_U_MENUorID(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор дочернего окна.

*hMenu*<br/>
Дескриптор меню.

### <a name="remarks"></a>Примечания

Аргумент для конструктора HMENU хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
