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
ms.openlocfilehash: 8f94322912dc8645c88d32ac721d35bd2deb70af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557434"
---
# <a name="ustringorid-class"></a>Класс _U_STRINGorID

Этот класс адаптера аргумент позволяет имена ресурсов (LPCTSTRs) или идентификаторы ресурсов (единицы), должны быть переданы функции, не требуя вызывающий объект, преобразуемый в строку с помощью макроса MAKEINTRESOURCE идентификатор.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
class _U_STRINGorID
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[_U_STRINGorID::_U_STRINGorID](#_u_stringorid___u_stringorid)|Конструктор.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[_U_STRINGorID::m_lpstr](#_u_stringorid__m_lpstr)|Идентификатор ресурса.|

## <a name="remarks"></a>Примечания

Этот класс предназначен для реализации оболочки для управления ресурсами Windows API, такие как [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea), [LoadIcon](/windows/desktop/api/winuser/nf-winuser-loadicona), и [LoadMenu](/windows/desktop/api/winuser/nf-winuser-loadmenua) функций, которые принимают Аргумент LPCTSTR, который может быть либо имя ресурса, либо его идентификатор.

Этот класс определяет две перегрузки конструктора: один принимает аргумент LPCTSTR, а другой принимает аргумент целое число без знака. Аргумент целое число без знака преобразуется в тип ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса MAKEINTRESOURCE и результата, хранимого в единый данные-член класса, [m_lpstr](#_u_stringorid__m_lpstr). Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="_u_stringorid__m_lpstr"></a>  _U_STRINGorID::m_lpstr

Класс содержит значение, передаваемое в любой из его конструкторов как открытый элемент данных LPCTSTR.

```
LPCTSTR m_lpstr;
```

##  <a name="_u_stringorid___u_stringorid"></a>  _U_STRINGorID::_U_STRINGorID

Конструктор целое число без знака преобразует свой аргумент к типу ресурса, совместимый с функциями управления ресурсами Windows, с помощью макроса MAKEINTRESOURCE и результат сохраняется в одном данные-член класса, [m_lpstr](#_u_stringorid__m_lpstr).

```
_U_STRINGorID(UINT nID);
_U_STRINGorID(LPCTSTR lpString);
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Идентификатор ресурса.

*lpString*<br/>
Имя ресурса.

### <a name="remarks"></a>Примечания

Аргумент для конструктора LPCTSTR хранится непосредственно без преобразования.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
