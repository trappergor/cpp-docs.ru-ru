---
title: CPaintDC-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9f83c36a9c1a0d334e3b4a75724521d5711123e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376539"
---
# <a name="cpaintdc-class"></a>CPaintDC-класс
Класс контекста устройства, производный от [CDC](../../mfc/reference/cdc-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|Создает `CPaintDC` подключен к заданному [CWnd](../../mfc/reference/cwnd-class.md).|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|Содержит [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) используется для рисования клиентской области.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND` К которому `CPaintDC` присоединен объект.|  
  
## <a name="remarks"></a>Примечания  
 Он выполняет [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) во время создания и [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) во время удаления.  
  
 Объект `CPaintDC` объект может использоваться только при ответе на [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) сообщения, обычно в вашей `OnPaint` функции-члена обработчик сообщений.  
  
 Дополнительные сведения об использовании `CPaintDC`, в разделе [контексты устройств](../../mfc/device-contexts.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC  
 Создает `CPaintDC` подготавливает окна приложения для рисования объектов и сохраняет [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) структуры в [m_ps](#m_ps) переменной-члена.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Параметры  
 `pWnd`  
 Указывает на `CWnd` объекта, к которому `CPaintDC` принадлежит объект.  
  
### <a name="remarks"></a>Примечания  
 Исключения (типа `CResourceException`) выдается, если Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) вызов завершается с ошибкой. На контекст устройства не могут быть доступны в том случае, если Windows уже выделена все контексты его доступных устройств. Приложение конкурирует за пять общих отображения контексты, доступные в любой момент времени в Windows.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd  
 `HWND` К которому `CPaintDC` присоединен объект.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>Примечания  
 `m_hWnd` защищенные переменная типа `HWND`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>  CPaintDC::m_ps  
 `m_ps` переменная открытый член типа [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md).  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>Примечания  
 Это `PAINTSTRUCT` , был передан и для заполнения [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint).  
  
 `PAINTSTRUCT` Содержит сведения, которые приложение использует для закрашивания клиентской области окна, связанные с `CPaintDC` объекта.  
  
 Обратите внимание на то, которому можно получить дескриптор контекста устройства через `PAINTSTRUCT`. Тем не менее, доступа к дескриптору напрямую через `m_hDC` переменной-члена, `CPaintDC` наследует от `CDC`.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [CPaintDC::m_hWnd](#m_hwnd).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC MDI](../../visual-cpp-samples.md)   
 [CDC-класс](../../mfc/reference/cdc-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



