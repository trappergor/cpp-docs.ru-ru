---
title: Класс CMDIChildWnd
ms.date: 11/04/2016
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
ms.openlocfilehash: 09a9846cc3d242ef7d812cb31b4dcdd515d5f6ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506081"
---
# <a name="cmdichildwnd-class"></a>Класс CMDIChildWnd

Предоставляет функции дочернего окна многодокументного интерфейса Windows (MDI) и элементы для управления окном.

## <a name="syntax"></a>Синтаксис

```
class CMDIChildWnd : public CFrameWnd
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMDIChildWnd:: CMDIChildWnd](#cmdichildwnd)|Создает объект `CMDIChildWnd`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMDIChildWnd:: Create](#create)|Создает дочернее окно Windows MDI, связанное с `CMDIChildWnd` объектом.|
|[CMDIChildWnd:: Жетмдифраме](#getmdiframe)|Возвращает родительский фрейм MDI окна клиента MDI.|
|[CMDIChildWnd:: Мдиактивате](#mdiactivate)|Активирует это дочернее окно MDI.|
|[CMDIChildWnd:: Мдидестрой](#mdidestroy)|Уничтожает это дочернее окно MDI.|
|[CMDIChildWnd:: Мдимаксимизе](#mdimaximize)|Разворачивает это дочернее окно MDI.|
|[CMDIChildWnd:: Мдиресторе](#mdirestore)|Восстанавливает дочернее окно MDI из развернутого или минимального размера.|
|[CMDIChildWnd:: Сесандлес](#sethandles)|Задает дескрипторы для ресурсов меню и ускорителя.|

## <a name="remarks"></a>Примечания

Дочернее окно MDI во многом похоже на обычное окно фрейма, за исключением того, что дочернее окно MDI отображается в окне фрейма MDI, а не на рабочем столе. Дочернее окно MDI не имеет собственной строки меню, а разделяет меню окна фрейма MDI. Платформа автоматически изменяет меню фрейма MDI для представления текущего активного дочернего окна MDI.

Чтобы создать полезное дочернее окно MDI для приложения, создайте класс, производный от `CMDIChildWnd`. Добавьте переменные члена в производный класс для хранения данных, относящихся к вашему приложению. Реализуйте в производном классе функции-члены обработчика сообщений и схему сообщений, чтобы указать, что происходит, когда сообщения направляются в окно.

Существует три способа создания дочернего окна MDI:

- Напрямую создавать его с `Create`помощью.

- Напрямую создавать его с `LoadFrame`помощью.

- Косвенно создать его с помощью шаблона документа.

Перед вызовом `Create` или `LoadFrame`необходимо создать объект окна фрейма в куче с помощью C++ оператора **New** . Перед вызовом `Create` можно также зарегистрировать класс окна с глобальной функцией [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) , чтобы задать стили значков и классов для фрейма.

Используйте функцию `Create` члена для передачи параметров создания кадра в качестве непосредственных аргументов.

`LoadFrame`требует меньше аргументов, `Create`чем, и вместо этого извлекает большинство значений по умолчанию из ресурсов, включая заголовок фрейма, значок, таблицу сочетаний клавиш и меню. Чтобы иметь доступ `LoadFrame`к, все эти ресурсы должны иметь один и тот же идентификатор ресурса (например, IDR_MAINFRAME).

`CMDIChildWnd` Если объект содержит представления и документы, они создаются косвенно платформой, а не непосредственно программистом. `CDocTemplate` Объект управляет созданием фрейма, созданием содержащихся представлений и подключением представлений к соответствующему документу. Параметры `CDocTemplate` конструктора указывают, `CRuntimeClass` какие из трех участвующих классов (документ, фрейм и представление). `CRuntimeClass` Объект используется платформой для динамического создания новых фреймов при их указании пользователем (например, с помощью команды файл создать или окна «создать»).

Класс фреймового окна, производный `CMDIChildWnd` от, должен быть объявлен с DECLARE_DYNCREATE, чтобы RUNTIME_CLASS механизм работал правильно.

Класс наследует большую часть своей реализации по умолчанию `CFrameWnd`из. `CMDIChildWnd` Подробный список этих функций см. в описании класса [CFrameWnd](../../mfc/reference/cframewnd-class.md) . `CMDIChildWnd` Класс имеет следующие дополнительные возможности:

- В сочетании с `CMultiDocTemplate` классом несколько `CMDIChildWnd` объектов из одного шаблона документа совместно используют одно и то же меню, сохраняя системные ресурсы Windows.

- Активное в настоящее время меню дочернего окна MDI полностью заменяет меню окна фрейма MDI, а заголовок текущего активного дочернего окна MDI добавляется в заголовок окна фрейма MDI. Дополнительные примеры функций дочерних окон MDI, реализованных в сочетании с окном фрейма MDI, см. в `CMDIFrameWnd` описании класса.

Не используйте C++ оператор **Delete** для уничтожения окна фрейма. Взамен рекомендуется использовать `CWnd::DestroyWindow`. `CFrameWnd` C++ Реализация объекта `PostNcDestroy` удалит объект при уничтожении окна. Когда пользователь закрывает окно фрейма, обработчик по `OnClose` умолчанию выполнит вызов `DestroyWindow`.

Дополнительные сведения о см `CMDIChildWnd`. в разделе [окна](../../mfc/frame-windows.md)с рамками.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cmdichildwnd"></a>CMDIChildWnd:: CMDIChildWnd

Вызовите метод, `CMDIChildWnd` чтобы создать объект.

```
CMDIChildWnd();
```

### <a name="remarks"></a>Примечания

Вызовите `Create` , чтобы создать видимое окно.

### <a name="example"></a>Пример

  См. пример для [CMDIChildWnd:: Create](#create).

##  <a name="create"></a>CMDIChildWnd:: Create

Вызовите эту функцию-член, чтобы создать дочернее окно Windows MDI и `CMDIChildWnd` присоединить его к объекту.

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,
    const RECT& rect = rectDefault,
    CMDIFrameWnd* pParentWnd = NULL,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзкласснаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая именует класс Windows (структуру [вндкласс](/windows/win32/api/winuser/ns-winuser-wndclassw) ). Имя класса может быть любым именем, зарегистрированным в глобальной функции [афксрегистервндкласс](application-information-and-management.md#afxregisterwndclass) . Для стандарта `CMDIChildWnd`должно быть задано значение null.

*лпсзвиндовнаме*<br/>
Указывает на строку символов, завершающуюся нулем, которая представляет имя окна. Используется в качестве текста для заголовка окна.

*двстиле*<br/>
Задает атрибуты [стиля](../../mfc/reference/styles-used-by-mfc.md#window-styles) окна. Требуется стиль WS_CHILD.

*rect*<br/>
Содержит размер и расположение окна. Это `rectDefault` значение позволяет Windows указать размер и расположение нового `CMDIChildWnd`объекта.

*ппарентвнд*<br/>
Задает родительский элемент окна. Если значение равно NULL, используется главное окно приложения.

*pContext*<br/>
Задает структуру [ккреатеконтекст](../../mfc/reference/ccreatecontext-structure.md) . Этот параметр может иметь значение NULL.

### <a name="return-value"></a>Возвращаемое значение

Имеет ненулевое значение в случае успешного выполнения, иначе — 0.

### <a name="remarks"></a>Примечания

В текущем активном окне дочернего фрейма MDI можно определить заголовок родительского окна фрейма. Эта функция отключена путем отключения бита стиля FWS_ADDTOTITLE в окне дочернего фрейма.

Платформа вызывает эту функцию-член в ответ на команду пользователя для создания дочернего окна, а платформа использует параметр *пконтекст* для правильного подключения дочернего окна к приложению. При вызове `Create`метод *пконтекст* может иметь значение null.

### <a name="example"></a>Пример

Пример 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>Пример

Пример 2

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>CMDIChildWnd:: Жетмдифраме

Вызовите эту функцию, чтобы вернуть родительский фрейм MDI.

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на окно родительского фрейма MDI.

### <a name="remarks"></a>Примечания

Возвращенный кадр состоит из двух родителей, удаленных `CMDIChildWnd` из и является родителем окна типа мдиклиент, которое `CMDIChildWnd` управляет объектом. Вызовите функцию-член- [родитель](../../mfc/reference/cwnd-class.md#getparent) , чтобы `CMDIChildWnd` вернуть непосредственный родительский мдиклиент объекта `CWnd` в качестве временного указателя.

### <a name="example"></a>Пример

  См. пример для [CMDIFrameWnd:: мдисетмену](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu).

##  <a name="mdiactivate"></a>CMDIChildWnd:: Мдиактивате

Вызовите эту функцию-член, чтобы активировать дочернее окно MDI независимо от окна фрейма MDI.

```
void MDIActivate();
```

### <a name="remarks"></a>Примечания

Когда кадр становится активным, также активируется дочернее окно, которое было активировано последним.

### <a name="example"></a>Пример

  См. пример для [CMDIFrameWnd:: жетвиндовменупопуп](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup).

##  <a name="mdidestroy"></a>CMDIChildWnd:: Мдидестрой

Вызовите эту функцию-член для уничтожения дочернего окна MDI.

```
void MDIDestroy();
```

### <a name="remarks"></a>Примечания

Функция члена удаляет заголовок дочернего окна из окна фрейма и деактивирует дочернее окно.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>CMDIChildWnd:: Мдимаксимизе

Вызовите эту функцию-член, чтобы развернуть дочернее окно MDI.

```
void MDIMaximize();
```

### <a name="remarks"></a>Примечания

Когда дочернее окно разворачивается, Windows изменяет его размер, чтобы заполнить клиентскую область окна фрейма. Windows помещает меню элемента управления дочернего окна в строке меню фрейма, чтобы пользователь мог восстановить или закрыть дочернее окно и добавить заголовок дочернего окна в заголовок фрейма окна.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>CMDIChildWnd:: Мдиресторе

Вызывайте эту функцию-член для восстановления дочернего окна MDI из развернутого или минимального размера.

```
void MDIRestore();
```

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>CMDIChildWnd:: Сесандлес

Задает дескрипторы для ресурсов меню и ускорителя.

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>Параметры

*hMenu*<br/>
Маркер ресурса меню.

*хакцел*<br/>
Маркер ресурса ускорителя.

### <a name="remarks"></a>Примечания

Вызовите эту функцию, чтобы задать ресурсы меню и ускорителя, используемые объектом дочернего окна MDI.

## <a name="see-also"></a>См. также

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример МДИДОКВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Пример СНАПВВ для MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CFrameWnd](../../mfc/reference/cframewnd-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CWnd](../../mfc/reference/cwnd-class.md)<br/>
[Класс CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)
