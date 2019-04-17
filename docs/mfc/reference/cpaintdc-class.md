---
title: Cpaintdc-класс
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
ms.openlocfilehash: df1db8a3e65d35f247df7d070119c66b02208815
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772063"
---
# <a name="cpaintdc-class"></a>Cpaintdc-класс

Класс контекста устройства, производный от [CDC](../../mfc/reference/cdc-class.md).

## <a name="syntax"></a>Синтаксис

```
class CPaintDC : public CDC
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CPaintDC::CPaintDC](#cpaintdc)|Создает `CPaintDC` подключен к указанным [CWnd](../../mfc/reference/cwnd-class.md).|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CPaintDC::m_ps](#m_ps)|Содержит [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) используется для рисования клиентской области.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[CPaintDC::m_hWnd](#m_hwnd)|HWND, к которому `CPaintDC` объект присоединен.|

## <a name="remarks"></a>Примечания

Он выполняет [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) во время создания и [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) во время уничтожения.

Объект `CPaintDC` объект может использоваться только при ответе на [WM_PAINT](/windows/desktop/gdi/wm-paint) сообщения, обычно в вашей `OnPaint` функция-член обработчика сообщений.

Дополнительные сведения об использовании `CPaintDC`, см. в разделе [контексты устройств](../../mfc/device-contexts.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CPaintDC`

## <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC

Создает `CPaintDC` подготавливает окна приложения для рисования объектов и сохраняет [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct) структуре [m_ps](#m_ps) переменной-члена.

```
explicit CPaintDC(CWnd* pWnd);
```

### <a name="parameters"></a>Параметры

*pWnd*<br/>
Указывает на `CWnd` объект, к которому `CPaintDC` принадлежит объект.

### <a name="remarks"></a>Примечания

Исключения (типа `CResourceException`) создается, если Windows [GetDC](/windows/desktop/api/winuser/nf-winuser-getdc) вызов завершается ошибкой. Контекст устройства не могут быть доступны в том случае, если Windows уже выделен все контексты его доступных устройств. Приложения конкурирует за пять общих отображения контексты, доступные в любой момент времени в группе Windows.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]

##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd

`HWND` К которому `CPaintDC` объект присоединен.

```
HWND m_hWnd;
```

### <a name="remarks"></a>Примечания

*m_hWnd* является защищенной переменной типа HWND.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]

##  <a name="m_ps"></a>  CPaintDC::m_ps

`m_ps` переменная открытый член типа [PAINTSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagpaintstruct).

```
PAINTSTRUCT m_ps;
```

### <a name="remarks"></a>Примечания

Это `PAINTSTRUCT` , передается в и для заполнения [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).

`PAINTSTRUCT` Содержит сведения, которые приложение использует для рисования клиентской области окна, связанный с `CPaintDC` объекта.

Обратите внимание на то, доступно ли дескриптор контекста устройства через `PAINTSTRUCT`. Тем не менее, доступа к дескриптору напрямую через `m_hDC` переменную-член, `CPaintDC` наследует от CDC.

### <a name="example"></a>Пример

  См. в примере [CPaintDC::m_hWnd](#m_hwnd).

## <a name="see-also"></a>См. также

[Пример MFC MDI](../../overview/visual-cpp-samples.md)<br/>
[Класс CDC](../../mfc/reference/cdc-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
