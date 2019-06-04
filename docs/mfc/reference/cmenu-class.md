---
title: CMenu-класс
ms.date: 11/04/2016
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
ms.openlocfilehash: 5df6515573cfca784d1e59f34342466dde2e42e4
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504848"
---
# <a name="cmenu-class"></a>CMenu-класс

Инкапсуляция `HMENU`Windows.

## <a name="syntax"></a>Синтаксис

```
class CMenu : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMenu::CMenu](#cmenu)|Создает объект `CMenu`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMenu::AppendMenu](#appendmenu)|Добавляет новый элемент в конец этого меню.|
|[CMenu::Attach](#attach)|Прикрепляет дескриптор меню Windows `CMenu` объекта.|
|[CMenu::CheckMenuItem](#checkmenuitem)|Устанавливает флажок рядом с полем или снимает флажок с пункта меню в контекстном меню.|
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Помещает типа "переключатель" рядом с элементом меню и лишается всех остальных пунктов меню в группе переключателя.|
|[CMenu::CreateMenu](#createmenu)|Создает пустое меню и присоединяет его к `CMenu` объекта.|
|[CMenu::CreatePopupMenu](#createpopupmenu)|Создает пустое всплывающее меню и присоединяет его к `CMenu` объекта.|
|[CMenu::DeleteMenu](#deletemenu)|Удаляет указанный элемент в меню. Если пункт меню имеет связанным всплывающего меню, Уничтожает дескриптор всплывающего меню и освобождает память, используемая в нем.|
|[CMenu::DeleteTempMap](#deletetempmap)|Удаляет все временные `CMenu` объекты, создаваемые `FromHandle` функция-член.|
|[CMenu::DestroyMenu](#destroymenu)|Уничтожает меню, подключенное к `CMenu` объект и освобождает память, занимаемую объектом меню.|
|[CMenu::Detach](#detach)|Отсоединяет дескриптор меню Windows из `CMenu` и возвращает дескриптор.|
|[CMenu::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида изменении определяемое владельцем меню.|
|[CMenu::EnableMenuItem](#enablemenuitem)|Включает, отключает или затемняется (оттенки серого) пункта меню.|
|[CMenu::FromHandle](#fromhandle)|Возвращает указатель на `CMenu` объект, заданный дескриптор меню Windows.|
|[CMenu::GetDefaultItem](#getdefaultitem)|Определяет элемент меню по умолчанию на заданное меню.|
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Извлекает идентификатор контекста справки, связанных с данным меню.|
|[CMenu::GetMenuInfo](#getmenuinfo)|Извлекает сведения о конкретных меню.|
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Определяет количество элементов меню всплывающее окно или верхнего уровня.|
|[CMenu::GetMenuItemID](#getmenuitemid)|Получает идентификатор пункта меню для пункта меню, расположенный в указанной позиции.|
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Извлекает сведения о пункте меню.|
|[CMenu::GetMenuState](#getmenustate)|Возвращает состояние указанного пункта меню или количество элементов во всплывающем меню.|
|[CMenu::GetMenuString](#getmenustring)|Извлекает подпись указанного пункта меню.|
|[CMenu::GetSafeHmenu](#getsafehmenu)|Возвращает `m_hMenu` обернутый `CMenu` объекта.|
|[CMenu::GetSubMenu](#getsubmenu)|Извлекает указатель на всплывающего меню.|
|[CMenu::InsertMenu](#insertmenu)|Вставляет новый элемент меню в указанной позиции, движение других элементов в меню.|
|[CMenu::InsertMenuItem](#insertmenuitem)|Вставляет новый элемент меню в указанной позиции в меню.|
|[CMenu::LoadMenu](#loadmenu)|Загружает ресурс меню из исполняемого файла и присоединяется к `CMenu` объекта.|
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Загружает меню из меню шаблона в памяти и присоединяет его к `CMenu` объекта.|
|[CMenu::MeasureItem](#measureitem)|Вызывается платформой для определения измерения меню, когда создается определяемое владельцем меню.|
|[CMenu::ModifyMenu](#modifymenu)|Изменяет существующий элемент меню в указанной позиции.|
|[CMenu::RemoveMenu](#removemenu)|Удаляет указанное меню пункта меню со связанным всплывающего меню.|
|[CMenu::SetDefaultItem](#setdefaultitem)|Задает элемент меню по умолчанию для указанного меню.|
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Задает идентификатор контекста справки, связываемое с меню.|
|[CMenu::SetMenuInfo](#setmenuinfo)|Задает сведения о конкретных меню.|
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Связывает точечные рисунки указанный флажок с пункта меню.|
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Изменение сведений о пункта меню.|
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Отображает всплывающее меню с плавающей запятой в указанном расположении и отслеживает выбор элементов всплывающего меню.|
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Отображает всплывающее меню с плавающей запятой в указанном расположении и отслеживает выбор элементов всплывающего меню.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CMenu::operator HMENU](#operator_hmenu)|Извлекает дескриптор объекта меню.|
|[CMenu::operator! =](#operator_neq)|Определяет, если два меню объекты не равны.|
|[CMenu::operator ==](#operator_eq_eq)|Определяет, равны ли два объекта меню.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CMenu::m_hMenu](#m_hmenu)|Указывает дескриптор меню Windows, подключенный к `CMenu` объекта.|

## <a name="remarks"></a>Примечания

Он предоставляет функции-члены для создания, отслеживания, обновления и уничтожение меню.

Создание `CMenu` объект в кадре стека как локальный, затем вызовите `CMenu`в функции-члены для управления в новое меню, при необходимости. Затем вызовите [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) для установки в меню окна, после чего сразу путем вызова `CMenu` объекта [отсоединения](#detach) функция-член. `CWnd::SetMenu` Функция-член задает меню "окно" новое меню перерисовку в соответствии с изменениями меню в окне и также передает владение меню окна. Вызов `Detach` отсоединяет HMENU из `CMenu` объекта, так что при локальном `CMenu` переменной выйдет за пределы области, `CMenu` деструктора объекта не будет пытаться удалить меню, больше не является владельцем. Само меню автоматически уничтожается при уничтожении окна.

Можно использовать [LoadMenuIndirect](#loadmenuindirect) для создания меню из шаблона в памяти, но меню, созданные из ресурса с помощью вызова функции-члена [LoadMenu](#loadmenu) повышает удобство поддержки и сам ресурс меню может быть создан и изменен с помощью редактора меню.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMenu`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="appendmenu"></a>  CMenu::AppendMenu

Добавляет новый элемент в конец меню.

```
BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL AppendMenu(
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nFlags*<br/>
Указывает сведения о состоянии нового элемента меню, при добавлении в меню. Он состоит из одного или нескольких значений, перечисленных в разделе "Примечания".

*nIDNewItem*<br/>
Указывает идентификатор команды нового элемента меню или, если *nFlags* присваивается MF_POPUP, дескриптор меню ( `HMENU`) из всплывающего меню. *NIDNewItem* параметр не учитывается (не требуется), если *nFlags* присваивается MF_SEPARATOR.

*lpszNewItem*<br/>
Указывает содержимое нового элемента меню. *NFlags* параметр используется для интерпретации *lpszNewItem* следующим образом:

|nFlags|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-разрядное значение, приложение можно использовать для обслуживания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение доступной для приложения, при обработке WM_MEASUREITEM и WM_DRAWITEM сообщений. Значение хранится в `itemData` член структуры, в состав этих сообщений.|
|MF_STRING|Содержит указатель на строку, завершающуюся символом null. Это Интерпретация по умолчанию.|
|MF_SEPARATOR|*LpszNewItem* параметр учитывается (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве пункта меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение может задать состояние элемента меню, установив значения в *nFlags*. Когда *nIDNewItem* указывает всплывающего меню, он становится частью меню, к которому он добавляется. Если соответствующее меню вышел из строя, пункты меню, добавленные также будут уничтожены. Пункты меню, добавленные следует отсоединить от `CMenu` , чтобы избежать конфликтов. Обратите внимание, что MF_STRING и MF_OWNERDRAW являются недопустимыми для точечного рисунка версии `AppendMenu`.

В следующем списке описываются флаги, которые могут быть заданы в *nFlags*:

- MF_CHECKED действует как переключатель с MF_UNCHECKED для размещения по умолчанию флажок рядом с элементом. Когда приложение предоставляет галочки точечные рисунки (см. в разделе [SetMenuItemBitmaps](#setmenuitembitmaps) функция-член), «флажок в» точечный рисунок отображается.

- MF_UNCHECKED действует как переключатель с MF_CHECKED снимите флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. в разделе `SetMenuItemBitmaps` функция-член), появляется точечный «флажок off».

- MF_DISABLED отключает пункт меню, чтобы он не может быть выбран, но не затемнять.

- MF_ENABLED позволяет пункта меню, чтобы его можно выбрать и восстанавливается из состояния серым цветом.

- MF_GRAYED отключает пункт меню, чтобы он не может быть выбран и затемняет его.

- MF_MENUBARBREAK помещает элемент на новой строке в статических меню или в новом столбце во всплывающих меню. Новый столбец всплывающего меню будут отделяться от старого вертикальной разделительной линии.

- MF_MENUBREAK помещает элемент на новой строке в статических меню или в новом столбце во всплывающих меню. Без разделительной линии помещается между столбцами.

- MF_OWNERDRAW указывает, что элемент является рисуемого владельцем элемента. При первом отображении меню, окна, которому принадлежит меню получает сообщение WM_MEASUREITEM, который получает высоту и ширину элемента меню. Сообщение WM_DRAWITEM является отправленного всякий раз, когда владелец необходимо обновить внешний вид пункта меню. Этот параметр не является допустимым для пункта меню верхнего уровня.

- MF_POPUP указывает, что пункт меню имеет всплывающего меню, связанные с ней. Параметр ID указывает дескриптор для раскрывающееся меню, которое должно быть связано с элементом. Используется для добавления иерархических всплывающего меню или всплывающего меню верхнего уровня для элемента всплывающего меню.

- MF_SEPARATOR рисует горизонтальной разделительной линии. Может использоваться только во всплывающем меню. Эта строка нельзя серым цветом, отключить или выделенным. Остальные параметры игнорируются.

- MF_STRING указывает, что пункт меню является символьной строкой.

Каждый из следующих групп перечислены флаги, которые являются взаимоисключающими и не могут использоваться вместе.

- MF_DISABLED MF_ENABLED и MF_GRAYED

- MF_STRING, MF_OWNERDRAW, MF_SEPARATOR и растровое изображение

- MF_MENUBARBREAK и MF_MENUBREAK

- MF_CHECKED и MF_UNCHECKED

Каждый раз, когда меню, которые находятся в окне изменяется (ли отображается в окне), приложение должно вызвать [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Пример

  См. в примере [CMenu::CreateMenu](#createmenu).

##  <a name="attach"></a>  CMenu::Attach

Присоединяет существующее меню Windows для `CMenu` объекта.

```
BOOL Attach(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Указывает дескриптор меню Windows.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если операция выполнена успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция не должны вызываться, если меню уже подключен к `CMenu` объекта. Дескриптор меню хранится в `m_hMenu` элемент данных.

Если вам нужен доступ к меню уже связан с окном, можно использовать [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) функцию, чтобы получить дескриптор для меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem

Добавляет галочки, или удаляет метки из пунктов меню в контекстном меню.

```
UINT CheckMenuItem(
    UINT nIDCheckItem,
    UINT nCheck);
```

### <a name="parameters"></a>Параметры

*nIDCheckItem*<br/>
Указывает пункт меню, чтобы проверить, что определяется *проверьте*.

*Проверьте*<br/>
Указывает, как проверить пункта меню и способ определения позиции элемента в меню. *Проверьте* параметр может быть комбинация из MF_CHECKED или MF_UNCHECKED с MF_BYPOSITION или MF_BYCOMMAND флагов. Эти флаги можно объединить с помощью битового оператора или. Они имеют следующий смысл:

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.

- MF_CHECKED действует как переключатель с MF_UNCHECKED для размещения по умолчанию флажок рядом с элементом.

- MF_UNCHECKED действует как переключатель с MF_CHECKED снимите флажок рядом с элементом.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние элемента: MF_CHECKED или MF_UNCHECKED или 0xFFFFFFFF, если элемент меню не существует.

### <a name="remarks"></a>Примечания

*NIDCheckItem* параметр указывает элемент, чтобы изменить.

*NIDCheckItem* параметр может быть зарегистрирована элемент всплывающего меню, а также пункта меню. Никакие специальные действия необходимы для проверки элемента всплывающего меню. Пункты меню верхнего уровня не может быть проверен. Необходимо установить флажок элемента всплывающего меню по позиции, так как он не имеет связанный с ним идентификатор пункта меню.

### <a name="example"></a>Пример

  См. в примере [CMenu::GetMenuState](#getmenustate).

##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem

Проверяет указанного пункта меню и делает его элементом переключателей.

```
BOOL CheckMenuRadioItem(
    UINT nIDFirst,
    UINT nIDLast,
    UINT nIDItem,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nIDFirst*<br/>
Указывает (как идентификатор или смещение, в зависимости от значения *nFlags*) первого элемента меню в группе переключателей.

*nIDLast*<br/>
Указывает (как идентификатор или смещение, в зависимости от значения *nFlags*) последнего элемента меню в группе переключателей.

*nIDItem*<br/>
Указывает (как идентификатор или смещение, в зависимости от значения *nFlags*) элемента в группу, которая будет проверяться с помощью типа "переключатель".

*nFlags*<br/>
Задает интерпретацию *nIDFirst*, *nIDLast*, и *nIDItem* следующим образом:

|nFlags|Интерпретация|
|------------|--------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае 0

### <a name="remarks"></a>Примечания

В то же время функция снимает все пункты меню в связанной группе и снимает флаг типа переключателей item для этих элементов. При отображении отмеченного элемента используется битовая карта переключателей кнопку (или маркер) вместо флажок растровое изображение.

### <a name="example"></a>Пример

  См. в примере [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).

##  <a name="cmenu"></a>  CMenu::CMenu

Создает пустое меню и присоединяет его к `CMenu` объекта.

```
CMenu();
```

### <a name="remarks"></a>Примечания

Меню не создается, пока вы вызовите один из создания или загрузки функции-члены `CMenu:`

- [Предоставил](#createmenu)

- [CreatePopupMenu](#createpopupmenu)

- [LoadMenu](#loadmenu)

- [LoadMenuIndirect](#loadmenuindirect)

- [Attach](#attach)

##  <a name="createmenu"></a>  CMenu::CreateMenu

Создается меню и присоединяет его к `CMenu` объекта.

```
BOOL CreateMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если меню создан успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню изначально пуста. Элементы меню можно добавлять с помощью `AppendMenu` или `InsertMenu` функция-член.

Если меню назначена к окну, автоматически уничтожается при уничтожении окна.

Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначен окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]

##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu

Создает всплывающее меню и присоединяет его к `CMenu` объекта.

```
BOOL CreatePopupMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, во всплывающем меню был успешно создан; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню изначально пуста. Элементы меню можно добавлять с помощью `AppendMenu` или `InsertMenu` функция-член. Приложение можно добавить во всплывающем меню в существующее меню или всплывающего меню. `TrackPopupMenu` Функция-член может использоваться для отображения этого меню как всплывающего меню с плавающей запятой и отслеживания выбранных элементов всплывающего меню.

Если меню назначена к окну, автоматически уничтожается при уничтожении окна. Если меню добавляется в существующее меню, автоматически уничтожается при уничтожении этого меню.

Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с помощью всплывающего меню, если меню не назначен окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функция-член.

### <a name="example"></a>Пример

  См. в примере [CMenu::CreateMenu](#createmenu).

##  <a name="deletemenu"></a>  CMenu::DeleteMenu

Удаляет элемент из меню.

```
BOOL DeleteMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nPosition*<br/>
Указывает элемент меню, которого необходимо удалить, как определено *nFlags*.

*nFlags*<br/>
Используется для интерпретации *nPosition* следующим образом:

|nFlags|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Если пункт меню имеет связанный всплывающего меню `DeleteMenu` Уничтожает дескриптор всплывающего меню и освобождает память, используемую во всплывающем меню.

Каждый раз, когда меню, которые находятся в окна изменяется (ли отображается в окне), то приложение должно вызвать [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).

### <a name="example"></a>Пример

  См. в примере [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap

Автоматически вызывается `CWinApp` обработчиком времени простоя, удаляет все временные `CMenu` объекты, создаваемые [FromHandle](#fromhandle) функция-член.

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>Примечания

`DeleteTempMap` Отсоединяет объект меню Windows, присоединенный к временным `CMenu` объекта перед удалением `CMenu` объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]

##  <a name="destroymenu"></a>  CMenu::DestroyMenu

Уничтожает меню и ресурсы Windows, которые были использованы.

```
BOOL DestroyMenu();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если уничтожается меню; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню отсоединяется от `CMenu` объекта перед его удалением. Windows `DestroyMenu` функция вызывается автоматически в `CMenu` деструктор.

### <a name="example"></a>Пример

  См. в примере [CMenu::CreateMenu](#createmenu).

##  <a name="detach"></a>  CMenu::Detach

Отсоединяет меню Windows `CMenu` объекта и возвращает дескриптор.

```
HMENU Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор типа дескриптора HMENU, в меню Windows, если выполнение прошло успешно; в противном случае имеет значение NULL.

### <a name="remarks"></a>Примечания

`m_hMenu` Элемент данных имеет значение NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]

##  <a name="drawitem"></a>  CMenu::DrawItem

Вызывается платформой при изменении внешнего вида изменении определяемое владельцем меню.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Параметры

*lpDrawItemStruct*<br/>
Указатель на [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct) структуру, содержащую сведения о типе документа требуется.

### <a name="remarks"></a>Примечания

`itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. Переопределите эту функцию-член для реализации рисования для рисуемого владельцем `CMenu` объекта. Приложение следует восстановить всех графических устройств (интерфейс) выбранных объектов контекста отображения, указано в *lpDrawItemStruct* до завершения операции этой функции-члена.

См. в разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание `DRAWITEMSTRUCT` структуры.

### <a name="example"></a>Пример

Приведенный ниже код взят из MFC [CTRLTEST](../../overview/visual-cpp-samples.md) пример:

[!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]

##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem

Включает, отключает или затемняется пункта меню.

```
UINT EnableMenuItem(
    UINT nIDEnableItem,
    UINT nEnable);
```

### <a name="parameters"></a>Параметры

*nIDEnableItem*<br/>
Указывает элемент меню, включение, что определяется *nEnable*. Этот параметр можно указать элементы всплывающего меню, а также стандартных элементов меню.

*nEnable*<br/>
Указывает действие, выполняемое. Он может представлять собой сочетание MF_DISABLED, MF_ENABLED или MF_GRAYED с MF_BYCOMMAND или MF_BYPOSITION. Эти значения могут объединяться с помощью битового оператора или. Эти значения имеют следующий смысл:

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.

- MF_DISABLED отключает пункт меню, чтобы он не может быть выбран, но не затемнять.

- MF_ENABLED позволяет пункта меню, чтобы его можно выбрать и восстанавливается из состояния серым цветом.

- MF_GRAYED отключает пункт меню, чтобы он не может быть выбран и затемняет его.

### <a name="return-value"></a>Возвращаемое значение

Предыдущее состояние (MF_DISABLED, MF_ENABLED или MF_GRAYED) или -1, если это не является допустимым.

### <a name="remarks"></a>Примечания

[Предоставил](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), и [LoadMenuIndirect](#loadmenuindirect) функции-члены также можно задать состояние (включена, отключен или недоступен) пункта меню.

С помощью значения MF_BYPOSITION требуется приложение с правильными `CMenu`. Если `CMenu` меню отрезок, затронутых элемент меню верхнего уровня (элемент в строке меню). Чтобы задать состояние элемента в всплывающее окно или вложенные всплывающего меню по позиции, приложение должно указать `CMenu` всплывающего меню.

Если приложение указывает флаг MF_BYCOMMAND, Windows проверяет все элементы всплывающего меню, подчиненных `CMenu`; таким образом, если отсутствуют дублированию пунктов, с помощью `CMenu` меню панели будет достаточно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]

##  <a name="fromhandle"></a>  CMenu::FromHandle

Возвращает указатель на `CMenu` объект, заданный дескриптор Windows в меню.

```
static CMenu* PASCAL FromHandle(HMENU hMenu);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Дескриптор меню Windows.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMenu` , может быть временным или постоянным.

### <a name="remarks"></a>Примечания

Если `CMenu` объект еще не присоединен к объекту меню Windows, временный `CMenu` созданный и присоединенный объект.

Этот временный `CMenu` объект действителен только до следующей встречи, в приложении есть время простоя в свой цикл событий, после чего будут удалены все временные объекты.

### <a name="example"></a>Пример

  См. в примере [CMenu::CreateMenu](#createmenu).

##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem

Определяет элемент меню по умолчанию на заданное меню.

```
UINT GetDefaultItem(
    UINT gmdiFlags,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*gmdiFlags*<br/>
Значение, указывающее, каким образом будет выполняться поиск для пунктов меню. Этот параметр может быть none, один или сочетания из следующих значений:

|Значение|Значение|
|-----------|-------------|
|GMDI_GOINTOPOPUPS|Указывает, что, если элемент по умолчанию открывается подменю, функции для поиска в соответствующих подменю рекурсивно. Если подменю имеет элемент по умолчанию отсутствует, возвращаемое значение определяет элемент, который открывает подменю.<br /><br /> По умолчанию функция возвращает первый элемент по умолчанию на заданное меню, независимо от того элемента, который открывается подменю.|
|GMDI_USEDISABLED|Указывает, что функция для возвращения элемента по умолчанию, даже если она отключена.<br /><br /> По умолчанию функция пропускает отключенные или затененный элементов.|

*fByPos*<br/>
Значение, указывающее, следует ли получить идентификатор пункта меню или его положение. Если этот параметр имеет значение FALSE, возвращается идентификатор. В противном случае возвращается позиция.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращает значение идентификатора или положение элемента меню. Если функция завершается с ошибкой, возвращается - 1.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение функции Win32 [GetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-getmenudefaultitem), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId

Извлекает контекст справки, идентификатор, связанный с `CMenu`.

```
DWORD GetMenuContextHelpId() const;
```

### <a name="return-value"></a>Возвращаемое значение

Контекстная справка, идентификатор, который в данный момент связанный с `CMenu` при его наличии; в противном случае — нуль.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo

Возвращает сведения о меню.

```
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;
```

### <a name="parameters"></a>Параметры

*lpcmi*<br/>
Указатель на [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) структуру, содержащую сведения для меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение не равно нулю; в противном случае возвращаемое значение равно нулю.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для получения сведений о меню.

##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount

Определяет количество элементов меню всплывающее окно или верхнего уровня.

```
UINT GetMenuItemCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в меню, если функция выполнена успешно; в противном случае-1.

### <a name="example"></a>Пример

  См. в примере [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).

##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID

Получает идентификатор пункта меню для пункта меню, который расположен в позиции, определяются *nPos*.

```
UINT GetMenuItemID(int nPos) const;
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Задает положение (начинающийся с нуля) элемента меню, идентификатор которого извлекается.

### <a name="return-value"></a>Возвращаемое значение

Идентификатор элемента для указанного элемента в всплывающего меню, если функция выполнена успешно. Если указанный элемент является всплывающим меню (в отличие от элемента в контекстном меню), возвращается значение-1. Если *nPos* соответствует пункту меню РАЗДЕЛИТЕЛЯ возвращаемое значение равно 0.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo

Извлекает сведения о пункте меню.

```
BOOL GetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Идентификатор или положение элемента меню, который требуется получить сведения. Значение этого параметра зависит от значения `ByPos`.

*lpMenuItemInfo*<br/>
Указатель на [MENUITEMINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuiteminfoa), как описано в пакете SDK для Windows, который содержит сведения о меню.

*fByPos*<br/>
Значение, указывающее значение `nIDItem`. По умолчанию `ByPos` равно FALSE, что указывает, что uItem — это идентификатор элемента меню. Если `ByPos` не задано значение false, указывает расположение элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращается ненулевое значение. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, используйте функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror), как описано в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение функции Win32 [GetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-getmenuiteminfoa), как описано в пакете Windows SDK. Обратите внимание, что в реализации MFC `GetMenuItemInfo`, вы не используете дескриптор для меню.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]

##  <a name="getmenustate"></a>  CMenu::GetMenuState

Возвращает состояние указанного пункта меню или количество элементов во всплывающем меню.

```
UINT GetMenuState(
    UINT nID,
    UINT nFlags) const;
```

### <a name="parameters"></a>Параметры

*nID*<br/>
Указывает идентификатор элемента меню, что определяется *nFlags*.

*nFlags*<br/>
Определяет характер *nID*. Он может принимать одно из следующих значений:

- MF_BYCOMMAND указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию.

- MF_BYPOSITION указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.

### <a name="return-value"></a>Возвращаемое значение

Значение 0xFFFFFFFF, если указанный элемент не существует. Если *nId* идентифицирует всплывающего меню, старший байт содержит количество элементов в контекстном меню, а младший байт меню флаги, связанные с во всплывающем меню. В противном случае возвращает значение маски (логическое или) значений из следующего списка (Эта маска описывает состояние меню элемент, который *nId* идентифицирует):

- MF_CHECKED действует как переключатель с MF_UNCHECKED для размещения по умолчанию флажок рядом с элементом. Когда приложение предоставляет галочки точечные рисунки (см. в разделе `SetMenuItemBitmaps` функция-член), «флажок в» точечный рисунок отображается.

- MF_DISABLED отключает пункт меню, чтобы он не может быть выбран, но не затемнять.

- MF_ENABLED позволяет пункта меню, чтобы его можно выбрать и восстанавливается из состояния серым цветом. Обратите внимание, что значение этой константы 0; приложения не должны протестировать 0 сбоев, при использовании этого значения.

- MF_GRAYED отключает пункт меню, чтобы он не может быть выбран и затемняет его.

- MF_MENUBARBREAK помещает элемент на новой строке в статических меню или в новом столбце во всплывающих меню. Новый столбец всплывающего меню будут отделяться от старого вертикальной разделительной линии.

- MF_MENUBREAK помещает элемент на новой строке в статических меню или в новом столбце во всплывающих меню. Без разделительной линии помещается между столбцами.

- MF_SEPARATOR рисует горизонтальной разделительной линии. Может использоваться только во всплывающем меню. Эта строка нельзя серым цветом, отключить или выделенным. Остальные параметры игнорируются.

- MF_UNCHECKED действует как переключатель с MF_CHECKED снимите флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. в разделе `SetMenuItemBitmaps` функция-член), появляется точечный «флажок off». Обратите внимание, что значение этой константы 0; приложения не должны протестировать 0 сбоев, при использовании этого значения.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]

##  <a name="getmenustring"></a>  CMenu::GetMenuString

Копирует метку указанного пункта меню в указанный буфер.

```
int GetMenuString(
    UINT nIDItem,
    LPTSTR lpString,
    int nMaxCount,
    UINT nFlags) const;

int GetMenuString(
    UINT nIDItem,
    CString& rString,
    UINT nFlags) const;
```

### <a name="parameters"></a>Параметры

*nIDItem*<br/>
Задает целочисленный идентификатор элемента меню или смещение для пункта меню в меню, в зависимости от значения *nFlags*.

*lpString*<br/>
Указывает на буфер, который должен получать метку.

*rString*<br/>
Ссылку на `CString` объекта, для получения скопированной меню строки.

*nMaxCount*<br/>
Указывает максимальную длину (в символах) метки для копирования. Если метка длиннее, чем максимальное количество, заданное в *nMaxCount*, дополнительные символы усекаются.

*nFlags*<br/>
Определяет интерпретацию *nIDItem* параметра. Он может принимать одно из следующих значений:

|nFlags|Интерпретация nIDItem|
|------------|-------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

### <a name="return-value"></a>Возвращаемое значение

Указывает фактическое число символов, копируемых в буфер, не включая завершающий символ null.

### <a name="remarks"></a>Примечания

*NMaxCount* параметр должен быть один больше, чем количество символов в метке, чтобы вместить нуль-символ, который завершает строку.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu

Возвращает дескриптора HMENU, инкапсулированный данным итератором `CMenu` объект или значение NULL`CMenu` указатель.

```
HMENU GetSafeHmenu() const;
```

### <a name="example"></a>Пример

  См. в примере [CMenu::LoadMenu](#loadmenu).

##  <a name="getsubmenu"></a>  CMenu::GetSubMenu

Извлекает `CMenu` объект всплывающего меню.

```
CMenu* GetSubMenu(int nPos) const;
```

### <a name="parameters"></a>Параметры

*nPos*<br/>
Указывает положение всплывающего меню, содержащихся в меню. Значения позиций начинаются с 0 для первого элемента меню. Идентификатор всплывающего меню не может использоваться в этой функции.

### <a name="return-value"></a>Возвращаемое значение

Указатель на `CMenu` которого `m_hMenu` член содержит дескриптор всплывающего меню, если существует всплывающего меню в заданной позиции; в противном случае — значение NULL. Если `CMenu` объект не существует, то временные он создается. `CMenu` Указатель, возвращенный не должны храниться.

### <a name="example"></a>Пример

  См. в примере [CMenu::TrackPopupMenu](#trackpopupmenu).

##  <a name="insertmenu"></a>  CMenu::InsertMenu

Вставляет новый элемент меню по позиции, заданной параметром *nPosition* и перемещает других элементов меню.

```
BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL InsertMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nPosition*<br/>
Задает элемент меню, перед которым является новый пункт меню для вставки. *NFlags* параметр может использоваться для интерпретации *nPosition* одним из следующих способов:

|nFlags|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0. Если *nPosition* равно -1, новый пункт меню добавляется в конец меню.|

*nFlags*<br/>
Указывает, каким образом *nPosition* интерпретируется и указывает сведения о состоянии нового элемента меню, когда он добавляется в меню. Список флагов, которые могут быть установлены, см. в разделе [функцию AppendMenu всегда](#appendmenu) функция-член. Чтобы указать более одного значения, используйте побитовый оператор OR их объединение с флагом MF_BYCOMMAND или MF_BYPOSITION.

*nIDNewItem*<br/>
Указывает идентификатор команды нового элемента меню или, если *nFlags* присваивается MF_POPUP, дескриптор меню (HMENU) во всплывающем меню. *NIDNewItem* параметр не учитывается (не требуется), если *nFlags* присваивается MF_SEPARATOR.

*lpszNewItem*<br/>
Указывает содержимое нового элемента меню. *nFlags* может использоваться для интерпретации *lpszNewItem* одним из следующих способов:

|nFlags|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-разрядное значение, приложение можно использовать для обслуживания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение для приложения в `itemData` член структуры, предоставляемые [WM_MEASUREITEM](/windows/desktop/Controls/wm-measureitem) и [WM_DRAWITEM](/windows/desktop/Controls/wm-drawitem) сообщений. Эти сообщения отправляются в том случае, когда элемент меню будет первоначально отображаться или изменении.|
|MF_STRING|Содержит длинный указатель на строку, завершающуюся символом null. Это Интерпретация по умолчанию.|
|MF_SEPARATOR|*LpszNewItem* параметр учитывается (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве пункта меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение может задать состояние элемента меню, установив значения в *nFlags*.

Каждый раз, когда меню, которые находятся в окне изменяется (ли отображается в окне), приложение должно вызвать `CWnd::DrawMenuBar`.

Когда *nIDNewItem* указывает всплывающего меню, он становится частью меню, в которой вставляется. Если соответствующее меню вышел из строя, вставленный меню также будут уничтожены. Вставленный меню следует отсоединить от `CMenu` , чтобы избежать конфликтов.

Если активная, развернуто дочернего окна многодокументного интерфейса (MDI) и приложение вставляет всплывающего меню в меню MDI-приложения путем вызова этой функции и указав флаг MF_BYPOSITION, меню вставки на одну позицию влево чем ожидается. Это происходит, поскольку в активную дочернюю MDI меню управления вставляется в первую позицию строки меню Окно области MDI. Для размещения меню должным образом, приложение необходимо добавить 1 к значению позиции, в противном случае будет использоваться. Приложение может использовать сообщение WM_MDIGETACTIVE для определения того, развернуто ли в данный момент активное дочернее окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]

##  <a name="insertmenuitem"></a>  CMenu::InsertMenuItem

Вставляет новый элемент меню в указанной позиции в меню.

```
BOOL InsertMenuItem(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
См. описание *uItem* в [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema) в пакете Windows SDK.

*lpMenuItemInfo*<br/>
См. описание *lpmii* в `InsertMenuItem` в пакете Windows SDK.

*fByPos*<br/>
См. описание *fByPosition* в `InsertMenuItem` в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция осуществляет [InsertMenuItem](/windows/desktop/api/winuser/nf-winuser-insertmenuitema), описанные в пакете Windows SDK.

##  <a name="loadmenu"></a>  CMenu::LoadMenu

Загружает ресурс меню из исполняемого файла приложения и присоединяет его к `CMenu` объекта.

```
BOOL LoadMenu(LPCTSTR lpszResourceName);
BOOL LoadMenu(UINT nIDResource);
```

### <a name="parameters"></a>Параметры

*lpszResourceName*<br/>
Указатель на заканчивающуюся нулем строку, содержащую имя ресурса меню для загрузки.

*nIDResource*<br/>
Указывает идентификатор ресурса меню меню загрузки.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если ресурс был загружен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначен окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]

##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect

Загружает ресурс на основе шаблона меню в памяти и присоединяет его к `CMenu` объекта.

```
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```

### <a name="parameters"></a>Параметры

*lpMenuTemplate*<br/>
Указывает шаблон меню (который представляет собой одну [MENUITEMTEMPLATEHEADER](/windows/desktop/api/winuser/ns-winuser-menuitemtemplateheader) структуры и коллекцию из одного или нескольких [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) структуры). Дополнительные сведения об этих двух структур см. в разделе Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если ресурс был загружен успешно; в противном случае 0.

### <a name="remarks"></a>Примечания

Меню шаблона является заголовком, следуют коллекцию из одного или нескольких [MENUITEMTEMPLATE](/windows/desktop/api/winuser/ns-winuser-menuitemtemplate) структуры, каждый из которых может содержать один или несколько пунктов меню, так и во всплывающих меню.

Номер версии должно быть равно 0.

`mtOption` Флаги должен включать MF_END последнего элемента в виде всплывающего списка, а также для последнего элемента в главном списке. См. в разделе `AppendMenu` функция-член для других флагов. `mtId` Член должен быть опущен из структуры MENUITEMTEMPLATE MF_POPUP, заданные в `mtOption`.

Место, выделенное для MENUITEMTEMPLATE структура должна быть достаточно большим для `mtString` должен содержать имя элемента меню в виде строку, завершающуюся символом null.

Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначен окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функция-член.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]

##  <a name="m_hmenu"></a>  CMenu::m_hMenu

Указывает дескриптор HMENU меню Windows, подключенный к `CMenu` объекта.

```
HMENU m_hMenu;
```

### <a name="example"></a>Пример

  См. в примере [CMenu::LoadMenu](#loadmenu).

##  <a name="measureitem"></a>  CMenu::MeasureItem

Вызывается платформой при создании меню с пользовательской отрисовки стиля.

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>Параметры

*lpMeasureItemStruct*<br/>
Указатель на `MEASUREITEMSTRUCT` структуры.

### <a name="remarks"></a>Примечания

По умолчанию эта функция-член ничего не делает. Переопределите эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows меню измерений.

См. в разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.

### <a name="example"></a>Пример

Приведенный ниже код взят из MFC [CTRLTEST](../../overview/visual-cpp-samples.md) пример:

[!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]

##  <a name="modifymenu"></a>  CMenu::ModifyMenu

Изменяет существующий элемент меню с позицией, заданной параметром *nPosition*.

```
BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem = 0,
    LPCTSTR lpszNewItem = NULL);

BOOL ModifyMenu(
    UINT nPosition,
    UINT nFlags,
    UINT_PTR nIDNewItem,
    const CBitmap* pBmp);
```

### <a name="parameters"></a>Параметры

*nPosition*<br/>
Задает элемент меню, которые необходимо изменить. *NFlags* параметр может использоваться для интерпретации *nPosition* одним из следующих способов:

|nFlags|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

*nFlags*<br/>
Указывает, каким образом *nPosition* интерпретируется, а также сведения о вносить изменения в элемент меню. Список флагов, которые могут быть установлены, см. в разделе [функцию AppendMenu всегда](#appendmenu) функция-член.

*nIDNewItem*<br/>
Указывает идентификатор команды меню измененного элемента или, если *nFlags* присваивается MF_POPUP, дескриптор меню (HMENU) из всплывающего меню. *NIDNewItem* параметр не учитывается (не требуется), если *nFlags* присваивается MF_SEPARATOR.

*lpszNewItem*<br/>
Указывает содержимое нового элемента меню. *NFlags* параметр может использоваться для интерпретации *lpszNewItem* одним из следующих способов:

|nFlags|Интерпретация lpszNewItem|
|------------|-----------------------------------|
|MF_OWNERDRAW|Содержит 32-разрядное значение, приложение можно использовать для обслуживания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение доступной для приложения, при обработке MF_MEASUREITEM и MF_DRAWITEM.|
|MF_STRING|Содержит длинный указатель на заканчивающуюся нулем строку или к `CString`.|
|MF_SEPARATOR|*LpszNewItem* параметр учитывается (не требуется).|

*pBmp*<br/>
Указывает на `CBitmap` объект, который будет использоваться в качестве пункта меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Приложение указывает новое состояние элемента меню, установив значения в *nFlags*. Если эта функция заменяет всплывающего меню, связанное с элементом меню, он удаляет старые во всплывающем меню и освобождает память, используемую во всплывающем меню.

Когда *nIDNewItem* указывает всплывающего меню, он становится частью меню, в которой вставляется. Если соответствующее меню вышел из строя, вставленный меню также будут уничтожены. Вставленный меню следует отсоединить от `CMenu` , чтобы избежать конфликтов.

Каждый раз, когда меню, которые находятся в окне изменяется (ли отображается в окне), приложение должно вызвать `CWnd::DrawMenuBar`. Чтобы изменить атрибуты существующих элементов меню, он работает намного быстрее использовать `CheckMenuItem` и `EnableMenuItem` функций-членов.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="operator_hmenu"></a>  CMenu::operator HMENU

Этот оператор используется для получения дескриптора элемента `CMenu` объекта.

```
operator HMENU() const;
```

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения дескриптор `CMenu` объекта; в противном случае — значение NULL.

### <a name="remarks"></a>Примечания

Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.

##  <a name="operator_neq"></a>  CMenu::operator! =

Определяет, если два меню логически не равны.

```
BOOL operator!=(const CMenu& menu) const;
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
Объект `CMenu` объект для сравнения.

### <a name="remarks"></a>Примечания

Проверяет объект меню с левой стороны не равен объекту меню справа от оператора.

##  <a name="operator_eq_eq"></a>  CMenu::operator ==

Определяет, логически равны ли два меню.

```
BOOL operator==(const CMenu& menu) const;
```

### <a name="parameters"></a>Параметры

*Меню*<br/>
Объект `CMenu` объект для сравнения.

### <a name="remarks"></a>Примечания

Проверяет объект меню в левой части равенство (с точки зрения значение HMENU) в объект меню справа от оператора.

##  <a name="removemenu"></a>  CMenu::RemoveMenu

Удаляет элемент меню со связанным всплывающее меню в меню.

```
BOOL RemoveMenu(
    UINT nPosition,
    UINT nFlags);
```

### <a name="parameters"></a>Параметры

*nPosition*<br/>
Указывает удаляемый элемент меню. *NFlags* параметр может использоваться для интерпретации *nPosition* одним из следующих способов:

|nFlags|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

*nFlags*<br/>
Указывает, каким образом *nPosition* интерпретируется.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Она не удаляет дескриптор всплывающего меню, поэтому можно повторно использовать меню. Перед вызовом этой функции, приложение может вызвать `GetSubMenu` функция-член для получения всплывающего окна `CMenu` объекта для повторного использования.

Каждый раз, когда меню, которые находятся в окна изменяется (ли отображается в окне), то приложение должно вызвать `CWnd::DrawMenuBar`.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem

Задает элемент меню по умолчанию для указанного меню.

```
BOOL SetDefaultItem(
    UINT uItem,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
Идентификатор или положение нового элемента меню по умолчанию или - 1 для нет элемента по умолчанию. Значение этого параметра зависит от значения *fByPos*.

*fByPos*<br/>
Значение, указывающее значение *uItem*. Если этот параметр имеет значение FALSE, *uItem* — это идентификатор элемента меню. В противном случае — это позиция элемента меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращается ненулевое значение. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, используйте функцию Win32 [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror), как описано в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция-член реализует поведение функции Win32 [SetMenuDefaultItem](/windows/desktop/api/winuser/nf-winuser-setmenudefaultitem), как описано в пакете Windows SDK.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId

Связывает идентификатор контекстной справки с `CMenu`.

```
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```

### <a name="parameters"></a>Параметры

*dwContextHelpId*<br/>
Идентификатор контекстной справки, связываемое с `CMenu`.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если выполнение прошло успешно; в противном случае 0

### <a name="remarks"></a>Примечания

Все элементы в меню используют этот идентификатор — это невозможно для присоединения в идентификатор контекста справки для отдельных пунктов меню.

### <a name="example"></a>Пример

  См. в примере [CMenu::InsertMenu](#insertmenu).

##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo

Задает информацию для меню.

```
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```

### <a name="parameters"></a>Параметры

*lpcmi*<br/>
Указатель на [MENUINFO](/windows/desktop/api/winuser/ns-winuser-tagmenuinfo) структуру, содержащую сведения для меню.

### <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение не равно нулю; в противном случае возвращаемое значение равно нулю.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать определенные сведения о меню.

##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps

Связывает указанный точечные рисунки с помощью пункта меню.

```
BOOL SetMenuItemBitmaps(
    UINT nPosition,
    UINT nFlags,
    const CBitmap* pBmpUnchecked,
    const CBitmap* pBmpChecked);
```

### <a name="parameters"></a>Параметры

*nPosition*<br/>
Задает элемент меню, которые необходимо изменить. *NFlags* параметр может использоваться для интерпретации *nPosition* одним из следующих способов:

|nFlags|Интерпретация nPosition|
|------------|---------------------------------|
|MF_BYCOMMAND|Указывает, что параметр дает идентификатор команды существующего элемента меню. Это значение по умолчанию, если задано значение MF_BYCOMMAND ни MF_BYPOSITION.|
|MF_BYPOSITION|Указывает, что параметр дает положение существующего элемента меню. Первый элемент находится в позиции 0.|

*nFlags*<br/>
Указывает, каким образом *nPosition* интерпретируется.

*pBmpUnchecked*<br/>
Указывает битовую карту для использования для пунктов меню, которые не проверяются.

*pBmpChecked*<br/>
Указывает битовую карту для использования для выделенных элементов меню.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если функция выполнена успешно; в противном случае — 0.

### <a name="remarks"></a>Примечания

Является ли элемент меню проверенный или непроверенный, Windows отображается соответствующий изображение рядом с элементом меню.

Если параметр *pBmpUnchecked* или *pBmpChecked* имеет значение NULL, то Windows не отображает ничего рядом с элементом меню для соответствующего атрибута. Если оба параметра имеют значение NULL, Windows использует флажок по умолчанию, когда элемент установлен и снимается флажок, если снят флажок элемента.

При уничтожении меню, эти точечные рисунки не уничтожаются; приложения должны уничтожить их.

Windows `GetMenuCheckMarkDimensions` функция Получает размеры флажок по умолчанию, используемый для пунктов меню. Приложение использует эти значения, чтобы определить соответствующий размер для растровых изображений, предоставленные с помощью этой функции. Получить размер, создайте точечные рисунки и установите их.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]

[!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]

##  <a name="setmenuiteminfo"></a>  CMenu::SetMenuItemInfo

Изменение сведений о пункта меню.

```
BOOL SetMenuItemInfo(
    UINT uItem,
    LPMENUITEMINFO lpMenuItemInfo,
    BOOL fByPos = FALSE);
```

### <a name="parameters"></a>Параметры

*uItem*<br/>
См. описание *uItem* в [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa) в пакете Windows SDK.

*lpMenuItemInfo*<br/>
См. описание *lpmii* в `SetMenuItemInfo` в пакете Windows SDK.

*fByPos*<br/>
См. описание *fByPosition* в `SetMenuItemInfo` в пакете Windows SDK.

### <a name="remarks"></a>Примечания

Эта функция осуществляет [SetMenuItemInfo](/windows/desktop/api/winuser/nf-winuser-setmenuiteminfoa), описанные в пакете Windows SDK.

##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu

Отображает всплывающее меню с плавающей запятой в указанном расположении и отслеживает выбор элементов всплывающего меню.

```
BOOL TrackPopupMenu(
    UINT nFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPCRECT lpRect = 0);
```

### <a name="parameters"></a>Параметры

*nFlags*<br/>
Указывает флаги положение на экране и положение указателя мыши. См. в разделе [метод TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) список доступных флагов.

*x*<br/>
Задает горизонтальное положение во всплывающем меню в экранных координатах. В зависимости от значения *nFlags* параметр меню может быть выравниванием по левому краю, по правому краю или по центру относительно этой позиции.

*y*<br/>
Задает вертикальное положение в экранных координатах в верхней части меню на экране.

*pWnd*<br/>
Определяет окно, которому принадлежит во всплывающем меню. Этот параметр не может иметь значение NULL, даже если указан флаг TPM_NONOTIFY. Это окно получает все сообщения WM_COMMAND в меню. В Windows 3.1 и более поздних версий, окно не получает сообщений WM_COMMAND до `TrackPopupMenu` возвращает. В Windows 3.0 окна получает сообщения WM_COMMAND перед `TrackPopupMenu` возвращает.

*lpRect*<br/>
Не обрабатывается.

### <a name="return-value"></a>Возвращаемое значение

Этот метод возвращает результат вызова метода [метод TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) в пакете Windows SDK.

### <a name="remarks"></a>Примечания

С плавающей запятой всплывающего меню может находиться в любом на экране.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]

##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx

Отображает всплывающее меню с плавающей запятой в указанном расположении и отслеживает выбор элементов всплывающего меню.

```
BOOL TrackPopupMenuEx(
    UINT fuFlags,
    int x,
    int y,
    CWnd* pWnd,
    LPTPMPARAMS lptpm);
```

### <a name="parameters"></a>Параметры

*fuFlags*<br/>
Указывает различные функции для расширенного меню. Список всех значений и их значениях см. в разделе [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

*x*<br/>
Задает горизонтальное положение во всплывающем меню в экранных координатах.

*y*<br/>
Задает вертикальное положение в экранных координатах в верхней части меню на экране.

*pWnd*<br/>
Указатель на окно-владелец во всплывающем меню и получения сообщений в созданный меню. Это окно может быть любое окно из текущего приложения, но не может иметь значение NULL. Если указать TPM_NONOTIFY в *fuFlags* параметра, функция не отправлять никаких сообщений для *pWnd*. Эта функция должна возвратить для окна, на которые указывают *pWnd* сообщение WM_COMMAND.

*lptpm*<br/>
Указатель на [TPMPARAMS](/windows/desktop/api/winuser/ns-winuser-tagtpmparams) структура, задающая область экрана меню не должны перекрываться. Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Если указать TPM_RETURNCMD в *fuFlags* параметр, возвращаемое значение является идентификатором пунктов меню элемента, выбранного пользователем. Если пользователь отменяет меню без выбора или при возникновении ошибки, возвращаемое значение равно 0.

Если вы не укажете TPM_RETURNCMD в *fuFlags* параметр, возвращаемое значение является ненулевым, если функция выполняется успешно и 0 в случае неудачи. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](/windows/desktop/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Примечания

С плавающей запятой всплывающего меню может находиться в любом на экране. Дополнительные сведения об обработке ошибок при создании всплывающих меню см. в разделе [TrackPopupMenuEx](/windows/desktop/api/winuser/nf-winuser-trackpopupmenuex).

## <a name="see-also"></a>См. также

[Пример MFC CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[Пример MFC DYNAMENU](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)
