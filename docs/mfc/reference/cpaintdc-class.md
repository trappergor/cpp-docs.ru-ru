---
title: Класс Кпаинтдк
ms.date: 11/04/2016
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
ms.openlocfilehash: d587f1cfa6ec38dd564da196da8130bffac11302
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69503140"
---
# <a name="cpaintdc-class"></a>Класс Кпаинтдк

Класс контекста устройства, производный от [CDC](../../mfc/reference/cdc-class.md).

## <a name="syntax"></a>Синтаксис

```
class CPaintDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Конструирует объект, `CPaintDC` подключенный к заданному [CWnd](../../mfc/reference/cwnd-class.md).|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[Кпаинтдк:: m_ps](#m_ps)|Содержит [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) , используемый для рисования клиентской области.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Кпаинтдк:: m_hWnd](#m_hwnd)|HWND, к которому присоединен `CPaintDC` этот объект.|

## <a name="remarks"></a>Примечания

Он выполняет [CWnd:: бегинпаинт](../../mfc/reference/cwnd-class.md#beginpaint) во время создания и [CWnd:: ендпаинт](../../mfc/reference/cwnd-class.md#endpaint) во время уничтожения.

Объект может использоваться только при ответе на сообщение [WM_PAINT](/windows/win32/gdi/wm-paint) `OnPaint` , обычно в функции-члене обработчика сообщений. `CPaintDC`

Дополнительные сведения об использовании `CPaintDC`см. в разделе контексты [устройств](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cpaintdc"></a>Кпаинтдк:: Кпаинтдк

Конструирует объект, готовит окно приложения для рисования и сохраняет структуру [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct) в переменной-члене [m_ps.](#m_ps) `CPaintDC`

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*Приводится*<br/>
Указывает на `CWnd` объект `CPaintDC` , которому принадлежит объект.

### <a name="remarks"></a>Примечания

Исключение (типа `CResourceException`) выдается при сбое вызова Windows [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) . Контекст устройства может быть недоступен, если в Windows уже выделены все доступные контексты устройств. Приложение будет конкурировать за пять распространенных контекстов вывода, доступных в любой момент в Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>Кпаинтдк:: m_hWnd

, `HWND` К которому присоединен `CPaintDC` этот объект.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

*m_hWnd* — это защищенная ПЕРЕМЕННАЯ типа HWND.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>Кпаинтдк:: m_ps

`m_ps`— Это открытая переменная-член типа [PAINTSTRUCT](/windows/win32/api/winuser/ns-winuser-paintstruct).

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Примечания

Это объект `PAINTSTRUCT` , который передается и заполняется методом [CWnd:: бегинпаинт](../../mfc/reference/cwnd-class.md#beginpaint).

Содержит сведения, используемые приложением для заполнения клиентской области окна, связанного `CPaintDC` с объектом. `PAINTSTRUCT`

Обратите внимание, что доступ к обработчику контекста устройства можно `PAINTSTRUCT`получить с помощью. Тем не менее можно получить доступ к этому обработчику напрямую `m_hDC` через переменную `CPaintDC` -член, которая наследуется от CDC.

### <a name="example"></a>Пример

  См. пример для [кпаинтдк:: m_hWnd](#m_hwnd).

## <a name="see-also"></a>См. также

[Образец MDI-формы MFC](../../overview/visual-cpp-samples.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
