---
title: CMenu-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64682066a93618c8646973c76df395883dddf053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378257"
---
# <a name="cmenu-class"></a>CMenu-класс
Инкапсуляция `HMENU`Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|Создает объект `CMenu`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|Добавляет новый элемент в конец этого меню.|  
|[CMenu::Attach](#attach)|Прикрепляет дескриптор меню Windows `CMenu` объекта.|  
|[CMenu::CheckMenuItem](#checkmenuitem)|Устанавливает флажок рядом с полем или удаляет метку из пункта меню в контекстном меню.|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Размещает переключатель рядом с элементом меню и удаляет переключатель от всех остальных пунктов меню в группе.|  
|[CMenu::CreateMenu](#createmenu)|Создает пустое меню и прикрепляет его к `CMenu` объекта.|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|Создает пустое всплывающего меню и прикрепляет его к `CMenu` объекта.|  
|[CMenu::DeleteMenu](#deletemenu)|Удаляет указанный элемент из меню. Если этот элемент меню имеет связанный всплывающего меню, Уничтожает дескриптор всплывающего меню и освобождает память, используется он.|  
|[CMenu::DeleteTempMap](#deletetempmap)|Удаляет все временные `CMenu` объектов, созданных `FromHandle` функции-члена.|  
|[CMenu::DestroyMenu](#destroymenu)|Уничтожает меню, присоединенные к `CMenu` объекта и освобождает память, занимаемую меню.|  
|[CMenu::Detach](#detach)|Отсоединяет дескриптор меню Windows из `CMenu` объекта и возвращает дескриптор.|  
|[CMenu::DrawItem](#drawitem)|Вызывается платформой при изменении внешнего вида пользовательского меню изменения.|  
|[CMenu::EnableMenuItem](#enablemenuitem)|Включает и отключает затемняет (оттенки серого) пункта меню.|  
|[CMenu::FromHandle](#fromhandle)|Возвращает указатель на `CMenu` объект, заданный дескриптор меню Windows.|  
|[CMenu::GetDefaultItem](#getdefaultitem)|Определяет элемент меню по умолчанию, указанным в меню.|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Извлекает идентификатор контекста справки, связанный с помощью меню.|  
|[CMenu::GetMenuInfo](#getmenuinfo)|Извлекает сведения о конкретных меню.|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Определяет количество элементов меню всплывающее окно или верхнего уровня.|  
|[CMenu::GetMenuItemID](#getmenuitemid)|Получает идентификатор пункта меню меню элемент, расположенный в указанной позиции.|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Извлекает сведения о пункта меню.|  
|[CMenu::GetMenuState](#getmenustate)|Возвращает состояние заданный элемент меню или количество элементов во всплывающем меню.|  
|[CMenu::GetMenuString](#getmenustring)|Получает метку заданный элемент меню.|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|Возвращает `m_hMenu` Инкапсулированный данным итератором `CMenu` объекта.|  
|[CMenu::GetSubMenu](#getsubmenu)|Извлекает указатель на всплывающего меню.|  
|[CMenu::InsertMenu](#insertmenu)|Вставляет новый элемент меню в указанной позиции, переместив другие элементы меню.|  
|[CMenu::InsertMenuItem](#insertmenuitem)|Вставляет новый элемент меню в указанной позиции в меню.|  
|[CMenu::LoadMenu](#loadmenu)|Загружает ресурс меню из исполняемого файла и прикрепляет его к `CMenu` объекта.|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Загружает меню из меню шаблона в памяти и прикрепляет его к `CMenu` объекта.|  
|[CMenu::MeasureItem](#measureitem)|Вызывается платформой для определения измерений меню, при создании пользовательского меню.|  
|[CMenu::ModifyMenu](#modifymenu)|Изменяет существующий элемент меню в указанной позиции.|  
|[CMenu::RemoveMenu](#removemenu)|Удаляет указанное меню пункта меню со связанным всплывающего меню.|  
|[CMenu::SetDefaultItem](#setdefaultitem)|Задает элемент меню по умолчанию для указанного меню.|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Задает идентификатор контекста справки, связываемое с помощью меню.|  
|[CMenu::SetMenuInfo](#setmenuinfo)|Задает сведения о конкретных меню.|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Связывает указанный флажок точечных рисунков с пунктом меню.|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Изменение сведений о пункта меню.|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Отображает число с плавающей контекстное меню в указанном месте и отслеживает список элементов всплывающего меню.|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Отображает число с плавающей контекстное меню в указанном месте и отслеживает список элементов всплывающего меню.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|Извлекает дескриптор объекта меню.|  
|[CMenu::operator! =](#operator_neq)|Определяет, если два меню объекты не равны.|  
|[CMenu::operator ==](#operator_eq_eq)|Определяет, равны ли два объекта меню.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|Указывает дескриптор меню Windows, присоединенного к `CMenu` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Он предоставляет функции-члены для создания, отслеживания, обновление и удаление меню.  
  
 Создание `CMenu` объект в кадре стека в качестве локального, затем вызовите `CMenu`его функции-члены для управления меню «Создать», при необходимости. Затем вызовите [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) для установки в меню в окне, за которым следует по вызов `CMenu` объекта [отсоединения](#detach) функции-члена. `CWnd::SetMenu` Функция-член задает меню "окно" новое меню, его окно перерисовки в соответствии с изменениями меню и также передает владение меню окна. Вызов **отсоединения** отсоединяет `HMENU` из `CMenu` объекта, так что при локальной `CMenu` переменной выйдет за пределы области, `CMenu` деструктора объекта не будет пытаться удалить меню его нет больше владеет. Само меню автоматически уничтожается при уничтожении окна.  
  
 Можно использовать [LoadMenuIndirect](#loadmenuindirect) Создание меню из шаблона в памяти, но меню, созданные из ресурса путем вызова функции-члена [LoadMenu](#loadmenu) повышает удобство поддержки, а сам ресурс меню может быть создан и изменен с помощью редактора меню.  
  
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
 `nFlags`  
 Указывает сведения о состоянии нового элемента меню при его добавлении в меню. Он состоит из одного или нескольких значений, перечисленных в разделе "Примечания".  
  
 `nIDNewItem`  
 Указывает идентификатор команды для нового пункта меню или, если `nFlags` равно **MF_POPUP**, дескриптор меню ( `HMENU`) из всплывающего меню. `nIDNewItem` Параметр не учитывается (не требуется), если `nFlags` равно **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Задает содержимое нового пункта меню. `nFlags` Параметр используется для интерпретации `lpszNewItem` следующим образом:  
  
|nFlags|Интерпретация lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Содержит 32-разрядное значение, приложение может использовать для поддержания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение доступны для приложения при его обработке `WM_MEASUREITEM` и `WM_DRAWITEM` сообщений. Значение, хранящееся в **itemData** член структуры, поставляемых вместе с этих сообщений.|  
|**MF_STRING**|Содержит указатель на строку, завершающуюся символом null. Это Интерпретация по умолчанию.|  
|**MF_SEPARATOR**|`lpszNewItem` Параметр учитывается (необязательно).|  
  
 *pBmp*  
 Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение может задать состояние элемента меню с помощью задания значения `nFlags`. Если `nIDNewItem` указывает всплывающего меню, оно становится частью меню, к которой добавляется. При уничтожении этого меню пункты меню, добавленные также будут уничтожены. Пункты меню, добавленные должны быть отсоединены от `CMenu` , чтобы избежать конфликтов. Обратите внимание, что **MF_STRING** и `MF_OWNERDRAW` являются недопустимыми для точечного рисунка версии `AppendMenu`.  
  
 В следующем списке описываются флаги, которые могут быть установлены в `nFlags`:  
  
- **MF_CHECKED** переключаться с **MF_UNCHECKED** для размещения по умолчанию флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. [SetMenuItemBitmaps](#setmenuitembitmaps) функции-члена), появляется точечный «флажок в».  
  
- **MF_UNCHECKED** переключаться с **MF_CHECKED** снимите флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. `SetMenuItemBitmaps` функции-члена), появляется точечный «флажок off».  
  
- **MF_DISABLED** отключает пункт меню, чтобы он не может быть выбран, но затемнять.  
  
- `MF_ENABLED` Включает элемент меню, чтобы он может быть выбран и его восстановления из состояния серым цветом.  
  
- **MF_GRAYED** отключает пункт меню, чтобы он не может быть выбран и затемняет его.  
  
- **MF_MENUBARBREAK** размещает элемент на новую строку в статических меню или в новый столбец во всплывающих меню. Новый столбец во всплывающем меню будут разделены от старого вертикальной Разделительная линия.  
  
- **MF_MENUBREAK** размещает элемент на новую строку в статических меню или в новый столбец во всплывающих меню. Без разделительной линии помещается между столбцами.  
  
- `MF_OWNERDRAW` Указывает, что элемент является рисуемый владельцем элемент. При первом отображении меню, окна, которому принадлежит меню получает `WM_MEASUREITEM` сообщение, которое получает высоту и ширину элемента меню. `WM_DRAWITEM` Сообщение является отправленного всякий раз, когда владелец необходимо обновить внешний вид пункта меню. Этот параметр недопустим для элемента меню верхнего уровня.  
  
- **MF_POPUP** указывает, что элемент меню имеет всплывающего меню, связанные с ним. Параметр ID указывает дескриптор всплывающего меню, который должен быть связан с элементом. Используется для добавления всплывающего меню верхнего уровня или иерархических всплывающего меню в пункт всплывающего меню.  
  
- **MF_SEPARATOR** рисует горизонтальной разделительной линии. Может использоваться только во всплывающем меню. Эта строка не может серым цветом, отключен или выделяются. Остальные параметры учитываются.  
  
- **MF_STRING** указывает, что пункт меню является символьная строка.  
  
 Каждый из следующих групп перечислены флаги, которые являются взаимоисключающими и не могут использоваться вместе.  
  
- **MF_DISABLED**, `MF_ENABLED`, и **MF_GRAYED**  
  
- **MF_STRING**, `MF_OWNERDRAW`, **MF_SEPARATOR**и версию растрового изображения  
  
- **MF_MENUBARBREAK** и **MF_MENUBREAK**  
  
- **MF_CHECKED** и **MF_UNCHECKED**  
  
 Каждый раз, когда меню, который находится в окне изменяется (ли окно отображается), приложение должно вызывать [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::CreateMenu](#createmenu).  
  
##  <a name="attach"></a>  CMenu::Attach  
 Присоединяет к существующему меню Windows `CMenu` объекта.  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 `hMenu`  
 Указывает дескриптор меню Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если операция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться, если меню уже присоединена к `CMenu` объекта. Дескриптор меню хранится в `m_hMenu` элемент данных.  
  
 Если меню, которую необходимо обработать уже связан с окном, можно использовать [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) функции, чтобы получить дескриптор для меню.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>  CMenu::CheckMenuItem  
 Добавляет флажки к или удаляет флажки из пунктов меню во всплывающем меню.  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDCheckItem`  
 Указывает пункт меню, чтобы проверить, что определяется `nCheck`.  
  
 `nCheck`  
 Указывает, как проверить элемент меню и способ определения позиции элемента в меню. `nCheck` Параметр может представлять собой сочетание **MF_CHECKED** или **MF_UNCHECKED** с **MF_BYPOSITION** или **MF_BYCOMMAND** флаги. Эти флаги можно объединить с помощью побитового оператора OR. Они имеют следующий смысл:  
  
- **MF_BYCOMMAND** указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию.  
  
- **MF_BYPOSITION** указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.  
  
- **MF_CHECKED** переключаться с **MF_UNCHECKED** для размещения по умолчанию флажок рядом с элементом.  
  
- **MF_UNCHECKED** переключаться с **MF_CHECKED** снимите флажок рядом с элементом.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее состояние элемента: **MF_CHECKED** или **MF_UNCHECKED**, или 0xFFFFFFFF, если элемент меню не существует.  
  
### <a name="remarks"></a>Примечания  
 `nIDCheckItem` Указывает элемент, чтобы изменить.  
  
 `nIDCheckItem` Параметра может быть зарегистрирована элемента всплывающего меню, а также пункта меню. Никакие специальные действия необходимы для проверки элемента всплывающего меню. Не удается вернуть пункты меню верхнего уровня. Элемент всплывающего меню должна быть проверена по позиции, так как он не имеет связанный с ним идентификатор пункта меню.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::GetMenuState](#getmenustate).  
  
##  <a name="checkmenuradioitem"></a>  CMenu::CheckMenuRadioItem  
 Проверяет указанный пункт меню и делает его элемент переключателей.  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `nIDFirst`  
 Указывает (как идентификатор или смещение, в зависимости от значения `nFlags`) первого элемента меню в группе переключателей.  
  
 `nIDLast`  
 Указывает (как идентификатор или смещение, в зависимости от значения `nFlags`) последнего элемента меню в группе переключателей.  
  
 `nIDItem`  
 Указывает (как идентификатор или смещение, в зависимости от значения `nFlags`) элемента в группу, которая будет проверяться с помощью типа "переключатель".  
  
 `nFlags`  
 Задает интерпретацию `nIDFirst`, `nIDLast`, и `nIDItem` следующим образом:  
  
|nFlags|Интерпретация|  
|------------|--------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 В то же время функция снимает все пункты меню в связанной группе и снимает флаг типа переключателей item для этих элементов. При отображении отмеченного элемента используется растровое изображение кнопки (или маркер) переключатель вместо растрового изображения галочки.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).  
  
##  <a name="cmenu"></a>  CMenu::CMenu  
 Создает пустое меню и прикрепляет его к `CMenu` объекта.  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>Примечания  
 Меню не создается, пока не будет вызван один из создать или загрузить функции-члены **CMenu:**  
  
- [Предоставил](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [Attach](#attach)  
  
##  <a name="createmenu"></a>  CMenu::CreateMenu  
 Создается меню и прикрепляет его к `CMenu` объекта.  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если меню был создан успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Меню изначально пуста. Элементы меню можно добавлять с помощью `AppendMenu` или `InsertMenu` функции-члена.  
  
 Если меню назначена к окну, автоматически уничтожается при уничтожении окна.  
  
 Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначены окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>  CMenu::CreatePopupMenu  
 Создание всплывающего меню и прикрепляет его к `CMenu` объекта.  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если во всплывающем меню был успешно создан; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Меню изначально пуста. Элементы меню можно добавлять с помощью `AppendMenu` или `InsertMenu` функции-члена. Приложение можно добавить во всплывающем меню к существующему меню или всплывающего меню. `TrackPopupMenu` Функция-член может использоваться для отображения этого меню как всплывающего меню с плавающей запятой и отслеживания выбранных элементов всплывающего меню.  
  
 Если меню назначена к окну, автоматически уничтожается при уничтожении окна. Если меню добавляется к существующему меню, автоматически уничтожается при уничтожении этого меню.  
  
 Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с всплывающего меню, если меню не назначены окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функции-члена.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::CreateMenu](#createmenu).  
  
##  <a name="deletemenu"></a>  CMenu::DeleteMenu  
 Удаляет элемент из меню.  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `nPosition`  
 Указывает элемент меню, которые требуется удалить, как определяется `nFlags`.  
  
 `nFlags`  
 Для интерпретации `nPosition` следующим образом:  
  
|nFlags|Интерпретация nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если этот элемент меню имеет связанный всплывающего меню `DeleteMenu` Уничтожает дескриптор всплывающего меню и освобождает память, используемые во всплывающем меню.  
  
 Каждый раз, когда меню, который находится в окне изменяется (ли окно отображается), приложение должно вызвать [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="deletetempmap"></a>  CMenu::DeleteTempMap  
 Автоматически вызывается `CWinApp` обработчиком времени простоя, удаляет все временные `CMenu` объектов, созданных [FromHandle](#fromhandle) функции-члена.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Примечания  
 `DeleteTempMap` Отсоединяет объект меню Windows, присоединенный к временным `CMenu` объекта перед удалением `CMenu` объекта.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>  CMenu::DestroyMenu  
 Уничтожает меню и все ресурсы Windows, которые были использованы.  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если меню удаляется; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Меню отсоединяется от `CMenu` объекта перед его удалением. Windows `DestroyMenu` функция вызывается автоматически в `CMenu` деструктор.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::CreateMenu](#createmenu).  
  
##  <a name="detach"></a>  CMenu::Detach  
 Отсоединяет меню Windows `CMenu` объекта и возвращает дескриптор.  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор типа `HMENU`, в меню Windows, если успешно; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 `m_hMenu` Член данных имеет значение **NULL**.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>  CMenu::DrawItem  
 Вызывается платформой при изменении внешнего вида пользовательского меню изменения.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpDrawItemStruct`  
 Указатель на [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) структуру, содержащую сведения о типе требуется рисования.  
  
### <a name="remarks"></a>Примечания  
 `itemAction` Членом `DRAWITEMSTRUCT` структура определяет рисования действие, которое должно быть выполнено. Переопределить эту функцию-член для реализации отрисовки рисуемый владельцем `CMenu` объекта. Приложения следует восстановить всех графических устройств (интерфейс) выбранных объектов контекст отображения указано в `lpDrawItemStruct` перед прекращением работы этой функции-члена.  
  
 В разделе [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) описание `DRAWITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 Следующий фрагмент кода взят из MFC [CTRLTEST](../../visual-cpp-samples.md) образца:  
  
 [!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>  CMenu::EnableMenuItem  
 Включает и отключает затемняет пункта меню.  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>Параметры  
 *nIDEnableItem*  
 Пункт меню, чтобы включить, указывает, что определяется `nEnable`. Этот параметр можно указать элементы всплывающего меню, а также стандартных элементов меню.  
  
 `nEnable`  
 Указывает действие, предпринимаемое. Он может представлять собой сочетание **MF_DISABLED**, `MF_ENABLED`, или **MF_GRAYED**, с **MF_BYCOMMAND** или **MF_BYPOSITION**. Эти значения могут быть объединены с помощью побитового оператора OR. Эти значения имеют следующий смысл:  
  
- **MF_BYCOMMAND** указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию.  
  
- **MF_BYPOSITION** указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.  
  
- **MF_DISABLED** отключает пункт меню, чтобы он не может быть выбран, но затемнять.  
  
- `MF_ENABLED` Включает элемент меню, чтобы он может быть выбран и его восстановления из состояния серым цветом.  
  
- **MF_GRAYED** отключает пункт меню, чтобы он не может быть выбран и затемняет его.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Предыдущее состояние ( **MF_DISABLED**, `MF_ENABLED`, или **MF_GRAYED**) или -1, если он не является допустимым.  
  
### <a name="remarks"></a>Примечания  
 [Предоставил](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), и [LoadMenuIndirect](#loadmenuindirect) функции-члены также можно задать состояние (включен, отключен или недоступен) пункта меню.  
  
 С помощью **MF_BYPOSITION** значения требуется приложение для использования правильного `CMenu`. Если `CMenu` меню используется панель, затронутых элемент меню верхнего уровня (элемент в строке меню). Чтобы задать состояние элемента во всплывающем меню всплывающее окно или вложенные по позиции, приложение должно указывать `CMenu` всплывающего меню.  
  
 Если приложение задает **MF_BYCOMMAND** флаг, Windows проверяет все элементы всплывающего меню, подчиненных `CMenu`; таким образом, только при наличии дублированию пунктов, с помощью `CMenu` меню является строка недостаточно.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>  CMenu::FromHandle  
 Возвращает указатель на `CMenu` объект, заданный дескриптор окна для меню.  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>Параметры  
 `hMenu`  
 Дескриптор меню Windows.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMenu` , которые могут быть постоянными или временными.  
  
### <a name="remarks"></a>Примечания  
 Если `CMenu` объект уже присоединен объект меню Windows временную `CMenu` объект создается и прикрепляется.  
  
 Этот временный `CMenu` объект действителен только до следующего приложение имеет время простоя в его цикл событий, после чего будут удалены все временные объекты.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::CreateMenu](#createmenu).  
  
##  <a name="getdefaultitem"></a>  CMenu::GetDefaultItem  
 Определяет элемент меню по умолчанию, указанным в меню.  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 *gmdiFlags*  
 Значение, указывающее, каким образом будет выполняться поиск пункта меню. Этот параметр может быть none, одно или сочетанием следующих значений:  
  
|Значение|Значение|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|Указывает, что, если элемент по умолчанию открывается подменю, функция является для поиска в соответствующих подменю рекурсивно. Если подменю нет элемента по умолчанию, возвращаемое значение определяет элемент, который открывает подменю.<br /><br /> По умолчанию функция возвращает первый элемент по умолчанию на указанное меню, независимо от того, является ли он элемента, который открывается подменю.|  
|**GMDI_USEDISABLED**|Указывает, что функция является для возвращения элемента по умолчанию, даже если она отключена.<br /><br /> По умолчанию функция пропускает элементы отключены или выделена серым цветом.|  
  
 `fByPos`  
 Значение, указывающее, следует ли получить идентификатор элемента меню или его положение. Если этот параметр имеет **FALSE**, возвращается идентификатор. В противном случае возвращается позиция.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение является идентификатором или положение данного элемента меню. Если функция завершается с ошибкой, возвращается - 1.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение функции Win32 [GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenucontexthelpid"></a>  CMenu::GetMenuContextHelpId  
 Получает контекстную справку, идентификатор, связанный с `CMenu`.  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Контекстная справка, идентификатор, который сейчас связан с `CMenu` при его наличии; в противном случае — нуль.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuinfo"></a>  CMenu::GetMenuInfo  
 Возвращает сведения о меню.  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `lpcmi`  
 Указатель на [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) структуру, содержащую сведения для меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение не равно нулю; в противном случае возвращаемое значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для получения сведений о меню.  
  
##  <a name="getmenuitemcount"></a>  CMenu::GetMenuItemCount  
 Определяет количество элементов меню всплывающее окно или верхнего уровня.  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в меню, если функция выполнена успешно; в противном случае значение -1.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="getmenuitemid"></a>  CMenu::GetMenuItemID  
 Получает идентификатор пункта меню меню элемент, расположенный в позиции, определенной `nPos`.  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Задает положение (начиная с нуля) элемента меню, идентификатор которого извлекается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор элемента для указанного элемента в всплывающего меню, если функция выполнена успешно. Если указанный элемент является всплывающим меню (в отличие от элемента в контекстном меню), возвращаемое значение равно -1. Если `nPos` соответствует **РАЗДЕЛИТЕЛЯ** пункт меню, возвращаемое значение равно 0.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuiteminfo"></a>  CMenu::GetMenuItemInfo  
 Извлекает сведения о пункта меню.  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `uItem`  
 Идентификатор или положение данного элемента меню для получения сведений о. Значение этого параметра зависит от значения `ByPos`.  
  
 `lpMenuItemInfo`  
 Указатель на [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578), как описано в Windows SDK, который содержит сведения о меню.  
  
 `fByPos`  
 Значение, указывающее значение `nIDItem`. По умолчанию `ByPos` — **FALSE**, указывающая, что uItem — это идентификатор элемента меню. Если `ByPos` равно **FALSE**, он указывает на позицию элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращается ненулевое значение. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, используйте функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), как описано в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение функции Win32 [GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980), как описано в Windows SDK. Обратите внимание, что в реализации MFC `GetMenuItemInfo`, не следует использовать дескриптор для меню.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>  CMenu::GetMenuState  
 Возвращает состояние заданный элемент меню или количество элементов во всплывающем меню.  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nID`  
 Указывает идентификатор элемента меню, как определено `nFlags`.  
  
 `nFlags`  
 Определяет характер `nID`. Он может принимать одно из следующих значений:  
  
- **MF_BYCOMMAND** указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию.  
  
- **MF_BYPOSITION** указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение 0xFFFFFFFF, если указанный элемент не существует. Если *nId* идентифицирует всплывающего меню, старший байт содержит число элементов в контекстном меню, а младший байт меню флаги, связанные с во всплывающем меню. В противном случае возвращает значение маски (логическое или) значений из следующего списка (Эта маска описывает состояние меню элементом, к которому *nId* идентифицирует):  
  
- **MF_CHECKED** переключаться с **MF_UNCHECKED** для размещения по умолчанию флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. `SetMenuItemBitmaps` функции-члена), появляется точечный «флажок в».  
  
- **MF_DISABLED** отключает пункт меню, чтобы он не может быть выбран, но затемнять.  
  
- `MF_ENABLED` Включает элемент меню, чтобы он может быть выбран и его восстановления из состояния серым цветом. Обратите внимание, что значение этой константы 0; приложения не должны проверить 0 в случае сбоя при использовании этого значения.  
  
- **MF_GRAYED** отключает пункт меню, чтобы он не может быть выбран и затемняет его.  
  
- **MF_MENUBARBREAK** размещает элемент на новую строку в статических меню или в новый столбец во всплывающих меню. Новый столбец во всплывающем меню будут разделены от старого вертикальной Разделительная линия.  
  
- **MF_MENUBREAK** размещает элемент на новую строку в статических меню или в новый столбец во всплывающих меню. Без разделительной линии помещается между столбцами.  
  
- **MF_SEPARATOR** рисует горизонтальной разделительной линии. Может использоваться только во всплывающем меню. Эта строка не может серым цветом, отключен или выделяются. Остальные параметры учитываются.  
  
- **MF_UNCHECKED** переключаться с **MF_CHECKED** снимите флажок рядом с элементом. Когда приложение предоставляет растровые изображения галочки (см. `SetMenuItemBitmaps` функции-члена), появляется точечный «флажок off». Обратите внимание, что значение этой константы 0; приложения не должны проверить 0 в случае сбоя при использовании этого значения.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>  CMenu::GetMenuString  
 Копирует подпись указанное меню элемента в указанный буфер.  
  
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
 `nIDItem`  
 Указывает целочисленный идентификатор элемента меню или смещение элемента меню в меню, в зависимости от значения `nFlags`.  
  
 `lpString`  
 Указатель на буфер, который должен получить метку.  
  
 `rString`  
 Ссылку на `CString` объекта, для получения строки копируются меню.  
  
 `nMaxCount`  
 Указывает максимальную длину (в символах) метки для копирования. Если метка превышает максимальное количество, заданное в `nMaxCount`, лишние символы усекаются.  
  
 `nFlags`  
 Определяет интерпретацию `nIDItem` параметра. Он может принимать одно из следующих значений:  
  
|nFlags|Интерпретация nIDItem|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указывает фактическое число символов, скопировать в буфер, не включая завершающий символ null.  
  
### <a name="remarks"></a>Примечания  
 `nMaxCount` Параметр должен иметь одно больше, чем количество символов в метке в соответствии с нуля, которая завершает строку.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getsafehmenu"></a>  CMenu::GetSafeHmenu  
 Возвращает `HMENU` Инкапсулированный данным итератором `CMenu` объекта, или **NULL** `CMenu` указателя.  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="getsubmenu"></a>  CMenu::GetSubMenu  
 Извлекает `CMenu` объекта из всплывающего меню.  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `nPos`  
 Задает положение всплывающего меню, содержащихся в меню. Значения позиций начинаются с 0 для первого элемента меню. Идентификатор всплывающего меню не может использоваться в этой функции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `CMenu` которого `m_hMenu` член содержит дескриптор всплывающего меню, если существует всплывающего меню в заданной позиции; в противном случае **NULL**. Если `CMenu` объект не существует, то создается временный один. `CMenu` Указатель, возвращенный не сохраняются.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::TrackPopupMenu](#trackpopupmenu).  
  
##  <a name="insertmenu"></a>  CMenu::InsertMenu  
 Вставляет новый пункт меню по позиции, указанной параметром `nPosition` и перемещает других элементов меню.  
  
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
 `nPosition`  
 Указывает элемент меню, до которого является новый пункт меню для вставки. `nFlags` Используется для интерпретации `nPosition` одним из следующих способов:  
  
|nFlags|Интерпретация nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0. Если `nPosition` равно -1, новый элемент меню добавляется в конец меню.|  
  
 `nFlags`  
 Указывает, каким образом `nPosition` интерпретируется и задает сведения о состоянии нового пункта меню при его добавлении в меню. Список флагов, которые могут быть установлены, в разделе [функцию AppendMenu всегда](#appendmenu) функции-члена. Чтобы указать более одного значения, используйте оператор побитового или объединить их с **MF_BYCOMMAND** или **MF_BYPOSITION** флаг.  
  
 `nIDNewItem`  
 Указывает идентификатор команды для нового пункта меню или, если `nFlags` равно **MF_POPUP**, дескриптор меню ( `HMENU`) из контекстного меню. `nIDNewItem` Параметр не учитывается (не требуется), если `nFlags` равно **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Задает содержимое нового пункта меню. `nFlags` можно использовать для интерпретации `lpszNewItem` одним из следующих способов:  
  
|nFlags|Интерпретация lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Содержит 32-разрядное значение, приложение может использовать для поддержания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение доступны для приложения в **itemData** член структуры, предоставляемые [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) и [WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923) сообщений. Эти сообщения отправляются в том случае, когда пункт меню сначала отображается или изменяется.|  
|**MF_STRING**|Содержит длинный указатель на строку, завершающуюся значением null. Это Интерпретация по умолчанию.|  
|**MF_SEPARATOR**|`lpszNewItem` Параметр учитывается (необязательно).|  
  
 *pBmp*  
 Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение может задать состояние элемента меню с помощью задания значения `nFlags`.  
  
 Каждый раз, когда меню, который находится в окне изменяется (ли окно отображается), приложение должно вызывать `CWnd::DrawMenuBar`.  
  
 Если `nIDNewItem` указывает всплывающего меню, оно становится частью меню, в которую вставляется. Если удаляется соответствующее меню, меню, вставленные также будут уничтожены. Меню, вставленные должны быть отсоединены от `CMenu` , чтобы избежать конфликтов.  
  
 Если активная развернуто дочернего окна многодокументного интерфейса (MDI) и приложение вставляет всплывающего меню в меню MDI-приложения, при вызове этой функции и указав **MF_BYPOSITION** вставляется флаг меню дальше на одну позицию влево, чем ожидалось. Это происходит, поскольку в активную дочернюю MDI меню управления вставляется в первую позицию строки меню Окно области MDI. Для размещения меню должным образом, приложение необходимо добавить 1 к значению позиции, в противном случае будет использоваться. Приложение может использовать **WM_MDIGETACTIVE** сообщения, чтобы определить, развернута ли в данный момент активным дочерним окном.  
  
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
 `uItem`  
 См. описание `uItem` в [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) в Windows SDK.  
  
 `lpMenuItemInfo`  
 См. описание `lpmii` в **InsertMenuItem** в Windows SDK.  
  
 `fByPos`  
 См. описание `fByPosition` в **InsertMenuItem** в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает оболочку для [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988), описанных в Windows SDK.  
  
##  <a name="loadmenu"></a>  CMenu::LoadMenu  
 Загружает ресурс меню из исполняемого файла приложения и прикрепляет его к `CMenu` объекта.  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszResourceName`  
 Указывает нулем строка, содержащая имя ресурса меню для загрузки.  
  
 `nIDResource`  
 Указывает идентификатор меню ресурс меню загрузки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот ресурс был загружен успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначены окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>  CMenu::LoadMenuIndirect  
 Загружает ресурс из меню шаблона в памяти и прикрепляет его к `CMenu` объекта.  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>Параметры  
 *lpMenuTemplate*  
 Указывает на шаблон меню (который представляет собой одну [MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583) структуры и коллекцию из одного или нескольких [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) структуры). Дополнительные сведения о этих двух структур см. в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если этот ресурс был загружен успешно. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Шаблон меню — это заголовок, следуют коллекцию из одного или нескольких [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) структур, каждая из которых может содержать один или несколько пунктов меню и контекстные меню.  
  
 Номер версии должно быть равно 0.  
  
 **MtOption** флаги должны включать **MF_END** последнего элемента в виде всплывающего списка, а также для последнего элемента в главном списке. В разделе `AppendMenu` функции-члена для других флагов. **MtId** член должна быть опущена из **MENUITEMTEMPLATE** структуры при **MF_POPUP** указывается в **mtOption**.  
  
 Место, выделенное для **MENUITEMTEMPLATE** структура должна быть достаточно большим для **mtString** содержит имя элемента меню в виде строку, завершающуюся символом null.  
  
 Перед завершением работы приложения необходимо освободить системные ресурсы, связанные с меню, если меню не назначены окна. Приложение освободит меню путем вызова [DestroyMenu](#destroymenu) функции-члена.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>  CMenu::m_hMenu  
 Указывает `HMENU` дескриптор меню Windows присоединяется к `CMenu` объекта.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="measureitem"></a>  CMenu::MeasureItem  
 Вызывается платформой при создании меню с стиль рисования владельцем.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Параметры  
 `lpMeasureItemStruct`  
 Указатель на `MEASUREITEMSTRUCT` структуры.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция-член не выполняет никаких действий. Переопределить эту функцию-член и заполните `MEASUREITEMSTRUCT` структуры для информирования Windows меню измерений.  
  
 В разделе [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) описание `MEASUREITEMSTRUCT` структуры.  
  
### <a name="example"></a>Пример  
 Следующий фрагмент кода взят из MFC [CTRLTEST](../../visual-cpp-samples.md) образца:  
  
 [!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>  CMenu::ModifyMenu  
 Изменяет существующий элемент меню в позиции, указанной параметром `nPosition`.  
  
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
 `nPosition`  
 Указывает элемент меню, которые необходимо изменить. `nFlags` Используется для интерпретации `nPosition` одним из следующих способов:  
  
|nFlags|Интерпретация nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
 `nFlags`  
 Указывает, каким образом `nPosition` интерпретируется, а также сведения об изменениях, внесенных в элемент меню. Список флагов, которые могут быть установлены, в разделе [функцию AppendMenu всегда](#appendmenu) функции-члена.  
  
 `nIDNewItem`  
 Указывает идентификатор команды пункта меню измененные или, если `nFlags` равно **MF_POPUP**, дескриптор меню ( `HMENU`) из всплывающего меню. `nIDNewItem` Параметр не учитывается (не требуется), если `nFlags` равно **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Задает содержимое нового пункта меню. `nFlags` Используется для интерпретации `lpszNewItem` одним из следующих способов:  
  
|nFlags|Интерпретация lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Содержит 32-разрядное значение, приложение может использовать для поддержания дополнительные данные, связанные с элементом меню предоставляемую приложением. Это 32-разрядное значение доступны для приложения при его обработке **MF_MEASUREITEM** и **MF_DRAWITEM**.|  
|**MF_STRING**|Содержит длинный указатель на строку, завершающуюся значением null или значение `CString`.|  
|**MF_SEPARATOR**|`lpszNewItem` Параметр учитывается (необязательно).|  
  
 *pBmp*  
 Указывает на `CBitmap` объект, который будет использоваться в качестве элемента меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Приложение указывает новое состояние элемента меню с помощью задания значения `nFlags`. Если эта функция заменяет всплывающего меню, связанное с элементом меню, он удаляет старые всплывающего меню и освобождает память, используемые во всплывающем меню.  
  
 Если `nIDNewItem` указывает всплывающего меню, оно становится частью меню, в которую вставляется. Если удаляется соответствующее меню, меню, вставленные также будут уничтожены. Меню, вставленные должны быть отсоединены от `CMenu` , чтобы избежать конфликтов.  
  
 Каждый раз, когда меню, который находится в окне изменяется (ли окно отображается), приложение должно вызывать `CWnd::DrawMenuBar`. Изменение атрибутов существующих элементов меню, намного быстрее использовать `CheckMenuItem` и `EnableMenuItem` функции-члены.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="operator_hmenu"></a>  CMenu::operator HMENU  
 Этот оператор используется для получения дескриптора `CMenu` объекта.  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения дескриптор `CMenu` объекта; в противном случае **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Дескриптор можно использовать для прямого вызова API-интерфейсов Windows.  
  
##  <a name="operator_neq"></a>  CMenu::operator! =  
 Определяет, если два меню логически не равны.  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `menu`  
 Объект `CMenu` объект для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет объект меню слева не равно объект меню справа от оператора.  
  
##  <a name="operator_eq_eq"></a>  CMenu::operator ==  
 Определяет, являются ли два меню логически равны.  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `menu`  
 Объект `CMenu` объект для сравнения.  
  
### <a name="remarks"></a>Примечания  
 Проверяет, равно объект меню слева (на основе `HMENU` значение) объект меню справа от оператора.  
  
##  <a name="removemenu"></a>  CMenu::RemoveMenu  
 Удаляет элемент меню со связанным всплывающего меню в меню.  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Параметры  
 `nPosition`  
 Указывает удаляемого элемента меню. `nFlags` Используется для интерпретации `nPosition` одним из следующих способов:  
  
|nFlags|Интерпретация nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
 `nFlags`  
 Указывает, каким образом `nPosition` интерпретируется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Она не удаляет дескриптор всплывающего меню, поэтому можно повторно использовать меню. Перед вызовом этой функции, приложение может вызвать `GetSubMenu` функции-члена для получения всплывающих окон `CMenu` объекта для повторного использования.  
  
 Каждый раз, когда меню, который находится в окне изменяется (ли окно отображается), приложение должно вызвать `CWnd::DrawMenuBar`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setdefaultitem"></a>  CMenu::SetDefaultItem  
 Задает элемент меню по умолчанию для указанного меню.  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 `uItem`  
 Идентификатор или позиция новый пункт меню по умолчанию или - 1 для элемента не по умолчанию. Значение этого параметра зависит от значения `fByPos`.  
  
 `fByPos`  
 Значение, указывающее значение `uItem`. Если этот параметр имеет **FALSE**, `uItem` — это идентификатор элемента меню. В противном случае — это положение пункта меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращается ненулевое значение. Если функция выполняется неудачно, возвращается нулевое значение. Чтобы получить расширенные сведения об ошибке, используйте функцию Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), как описано в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член реализует поведение функции Win32 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996), как описано в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenucontexthelpid"></a>  CMenu::SetMenuContextHelpId  
 Связывает идентификатор контекста справки с `CMenu`.  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Параметры  
 `dwContextHelpId`  
 Идентификатор контекста справки для связи с `CMenu`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Все элементы в меню, совместно использовать этот идентификатор — не удается присоединить идентификатор контекста справки для отдельных пунктов меню.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenuinfo"></a>  CMenu::SetMenuInfo  
 Задает сведения для меню.  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>Параметры  
 `lpcmi`  
 Указатель на [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) структуру, содержащую сведения для меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если функция выполняется успешно, возвращаемое значение не равно нулю; в противном случае возвращаемое значение равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Вызывайте эту функцию, чтобы задать определенные сведения о меню.  
  
##  <a name="setmenuitembitmaps"></a>  CMenu::SetMenuItemBitmaps  
 Связывает указанный растровых изображений с элементом меню.  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>Параметры  
 `nPosition`  
 Указывает элемент меню, которые необходимо изменить. `nFlags` Используется для интерпретации `nPosition` одним из следующих способов:  
  
|nFlags|Интерпретация nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Указывает, что параметр дает идентификатор команды для существующего элемента меню. Это значение по умолчанию, если ни одна из **MF_BYCOMMAND** , ни **MF_BYPOSITION** имеет значение.|  
|**MF_BYPOSITION**|Указывает, что параметр дает расположение существующего элемента меню. Первый элемент находится в положении 0.|  
  
 `nFlags`  
 Указывает, каким образом `nPosition` интерпретируется.  
  
 `pBmpUnchecked`  
 Указывает битовую карту для пунктов меню, которые не проверяются.  
  
 `pBmpChecked`  
 Указывает битовую карту для выделенных элементов меню.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Является ли элемент меню флажком, Windows выводит соответствующие растровое изображение рядом с пунктом меню.  
  
 Если параметр `pBmpUnchecked` или `pBmpChecked` — **NULL**, то Windows не отображает ничего рядом с пунктом меню для соответствующего атрибута. Если оба параметра имеют **NULL**, Windows использует флажок по умолчанию, когда элемент проверяется и снимает флажок, если элемент не установлен.  
  
 При удалении меню эти битовые карты, не удаляются; приложение должно удалить их.  
  
 Windows **GetMenuCheckMarkDimensions** функция извлекает размеры флажок по умолчанию, используемый для элементов меню. Приложение использует эти значения для определения подходящего размера для растровых изображений, предоставленные с помощью этой функции. Получение сведений о размере, создавать точечные рисунки и затем устанавливает для них.  
  
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
 `uItem`  
 См. описание `uItem` в [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) в Windows SDK.  
  
 `lpMenuItemInfo`  
 См. описание `lpmii` в **SetMenuItemInfo** в Windows SDK.  
  
 `fByPos`  
 См. описание `fByPosition` в **SetMenuItemInfo** в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 Эта функция создает оболочку для [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001), описанных в Windows SDK.  
  
##  <a name="trackpopupmenu"></a>  CMenu::TrackPopupMenu  
 Отображает число с плавающей контекстное меню в указанном месте и отслеживает список элементов всплывающего меню.  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nFlags`  
 Задает флаги, положение на экране и расположении мыши. В разделе [метод TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) список доступных флагов.  
  
 *x*  
 Задает горизонтальное положение всплывающего меню в экранных координатах. В зависимости от значения `nFlags` параметр меню можно по левому краю, по правому краю или по центру относительно этой позиции.  
  
 *y*  
 Задает вертикальное положение в экранных координатах вверху меню на экране.  
  
 `pWnd`  
 Идентифицирует окно, которому принадлежит во всплывающем меню. Этот параметр не может быть **NULL**, даже если **TPM_NONOTIFY** установлен флаг. Это окно получает все **WM_COMMAND** сообщения в меню. В системе Windows версии 3.1 и более поздней версии, не получает окна **WM_COMMAND** сообщений до `TrackPopupMenu` возвращает. В Windows 3.0, то оно получит **WM_COMMAND** сообщений перед `TrackPopupMenu` возвращает.  
  
 `lpRect`  
 Не обрабатывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает результат вызова [метод TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) в Windows SDK.  
  
### <a name="remarks"></a>Примечания  
 С плавающей запятой всплывающего меню может находиться в любом на экране.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>  CMenu::TrackPopupMenuEx  
 Отображает число с плавающей контекстное меню в указанном месте и отслеживает список элементов всплывающего меню.  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>Параметры  
 `fuFlags`  
 Указывает различные функции для расширенного меню. Список всех значений и их значение см. в разделе [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
 *x*  
 Задает горизонтальное положение всплывающего меню в экранных координатах.  
  
 *y*  
 Задает вертикальное положение в экранных координатах вверху меню на экране.  
  
 `pWnd`  
 Указатель на окно-владелец во всплывающем меню и получения сообщений из созданного меню. В этом окне может быть любое окно из текущего приложения, но не может быть **NULL**. При указании **TPM_NONOTIFY** в `fuFlags` параметр функции не отправлять сообщения для `pWnd`. Эта функция должна возвращать для окна, на который указывает `pWnd` получать **WM_COMMAND** сообщения.  
  
 *lptpm*  
 Указатель на [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586) структуру, которая указывает область экрана меню не должны перекрываться. Этот параметр может иметь **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 При указании **TPM_RETURNCMD** в `fuFlags` параметр, возвращаемое значение имеет идентификатор элемента, выбранного пользователем пункта меню. Если пользователь отменяет меню без выбора или при возникновении ошибки, возвращаемое значение — 0.  
  
 Если вы не укажете **TPM_RETURNCMD** в `fuFlags` параметр, возвращаемое значение является ненулевое значение, если функция выполняется успешно и 0 в случае неудачи. Чтобы получить расширенные сведения об ошибке, вызовите [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Примечания  
 С плавающей запятой всплывающего меню может находиться в любом на экране. Дополнительные сведения об обработке ошибок при создании всплывающих меню см. в разделе [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CTRLTEST](../../visual-cpp-samples.md)   
 [Пример MFC DYNAMENU](../../visual-cpp-samples.md)   
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CObject](../../mfc/reference/cobject-class.md)
