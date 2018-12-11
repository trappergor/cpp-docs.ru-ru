---
title: Класс CWinFormsControl
ms.date: 11/04/2016
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
ms.openlocfilehash: e8728c876badcf6648740cc842a1f289789bf0f4
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178243"
---
# <a name="cwinformscontrol-class"></a>Класс CWinFormsControl

Предоставляет базовую функцию для размещения элементов управления Windows Forms.

## <a name="syntax"></a>Синтаксис

```
template<class TManagedControl>
class CWinFormsControl : public CWnd
```

#### <a name="parameters"></a>Параметры

*TManagedControl*<br/>
Элемент управления .NET Framework Windows Forms для отображения в приложении MFC.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Создает объект управления оболочки MFC Windows Forms.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Создает элемент управления Windows Forms в контейнере MFC.|
|[CWinFormsControl::GetControl](#getcontrol)|Извлекает указатель на элемент управления Windows Forms.|
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Извлекает дескриптор элемента управления в Windows Forms.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.|
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Приводит тип указателя на элемент управления Windows Forms.|

## <a name="remarks"></a>Примечания

`CWinFormsControl` Класс предоставляет основные функциональные возможности для размещения элементов управления Windows Forms.

Дополнительные сведения об использовании Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

Код MFC не следует кэшировать дескрипторов окон (обычно хранится в `m_hWnd`). Некоторые свойства элемента управления Windows Forms требуют базовых Win32 `Window` быть уничтожается и создается заново с помощью `DestroyWindow` и `CreateWindow`. Реализация обрабатывает MFC Windows Forms `Destroy` и `Create` событий элементов управления, чтобы обновить `m_hWnd` член.

> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC (в котором определен AFXDLL).

## <a name="requirements"></a>Требования

**Заголовок:** afxwinforms.h

##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl

Создает элемент управления Windows Forms в контейнере MFC.

```
inline BOOL CreateManagedControl(
    System::Type^ pType,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID)
inline BOOL CreateManagedControl(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);

inline BOOL CreateManagedControl(
    DWORD dwStyle,
    int nPlaceHolderID,
    CWnd* pParentWnd);

inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID);
```

### <a name="parameters"></a>Параметры

*pType*<br/>
Тип данных создаваемого элемента управления. Должно быть [тип](https://msdn.microsoft.com/library/system.type) тип данных.

*dwStyle*<br/>
Стиль окна, чтобы применить к элементу управления. Укажите сочетание [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). В настоящее время поддерживаются только следующие стили: WS_TABSTOP, WS_VISIBLE, WS_DISABLED и WS_GROUP.

*rect*<br/>
Объект [структура RECT](/windows/desktop/api/windef/ns-windef-tagrect) , определяющий координаты верхнего левого и правого нижнего углов элемента управления (первая перегрузка только).

*nPlaceHolderID*<br/>
Дескриптор элемента управления держатель статический месте помещаются в редакторе ресурсов. Вновь созданный элемент управления Windows Forms заменяет статический элемент управления, при условии, что его позиции z порядок и стили (вторая перегрузка только).

*pParentWnd*<br/>
Указатель на родительское окно.

*nID*<br/>
Идентификатор ресурса должен назначаться только что созданный элемент управления.

*pControl*<br/>
Экземпляр элемента управления Windows Forms должно быть связано с [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) объекта (только для четвертая перегрузки).

### <a name="return-value"></a>Возвращаемое значение

В случае успешного выполнения возвращает ненулевое значение. Если операция завершилась неудачей, возвращает нуль.

### <a name="remarks"></a>Примечания

Этот метод создает экземпляр элемента управления .NET Framework Windows Forms в контейнеров MFC.

Первая перегрузка метода принимает тип данных .NET Framework *pType* таким образом, чтобы MFC можно создать новый объект этого типа. *pType* должно быть [тип](https://msdn.microsoft.com/library/system.type) тип данных.

Вторая перегрузка метода создает элемент управления Windows Forms, на основе `TManagedControl` параметр шаблона `CWinFormsControl` класса. Размер и положение элемента управления основан на `RECT` структуры передается в метод. Только *dwStyle* имеет значение для стилей.

Третья перегрузка метода создает элемент управления Windows Forms, который заменяет статический элемент управления, его уничтожение и при условии, что его позиции z порядок и стили. Статический элемент управления используется только как заполнитель для элемента управления Windows Forms. При создании элемента управления, эта перегрузка сочетание стилей из *dwStyle* с использованием стилей ресурсов статический элемент управления.

Четвертый перегрузка метода позволяет передавать в готовый элемент управления Windows Forms *pControl* , будет переносить MFC. Он должен иметь тот же тип, что `TManagedControl` параметр шаблона `CWinFormsControl` класса.

См. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) примеры с использованием формы Windows управляет.

##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl

Создает объект управления оболочки MFC Windows Forms.

```
CWinFormsControl();
```

### <a name="remarks"></a>Примечания

Элемент управления Windows Forms создается при вызове [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

##  <a name="getcontrol"></a>  CWinFormsControl::GetControl

Извлекает указатель на элемент управления Windows Forms.

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на элемент управления Windows Forms.

### <a name="example"></a>Пример

  См. в разделе [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).

##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle

Извлекает дескриптор элемента управления в Windows Forms.

```
inline HWND GetControlHandle() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает дескриптор элемента управления в Windows Forms.

### <a name="remarks"></a>Примечания

`GetControlHandle` — Это вспомогательный метод, который возвращает дескриптор окна, хранятся в свойствах элемента управления .NET Framework. Копируется значение дескриптора окна [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) во время вызова [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).

##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;

Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.

```
inline TManagedControl^  operator->() const;
```

### <a name="remarks"></a>Примечания

Этот оператор предоставляет удобный синтаксис, который заменяет `GetControl` в выражениях.

Дополнительные сведения о Windows Forms, см. в разделе [использование пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^

Приводит тип указателя на элемент управления Windows Forms.

```
inline operator TManagedControl^() const;
```

### <a name="remarks"></a>Примечания

Этот оператор передает `CWinFormsControl<TManagedControl>` функций, которые принимают указатель на элемент управления Windows Forms.

## <a name="see-also"></a>См. также

[Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)<br/>
[Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)
