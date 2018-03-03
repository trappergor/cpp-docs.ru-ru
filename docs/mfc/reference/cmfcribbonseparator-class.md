---
title: "Класс CMFCRibbonSeparator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36f05d89388d8722fab7853dc3c1e5bcb4d9a2f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcribbonseparator-class"></a>Класс CMFCRibbonSeparator
Реализует разделителя ленты.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|Создает объект `CMFCRibbonSeparator`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|Добавляет разделитель для **команды** списка в **Настройка** диалоговое окно. (Переопределяет [CMFCRibbonBaseElement::AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox).)|  
|`CMFCRibbonSeparator::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonSeparator::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание:|  
|[CMFCRibbonSeparator::CopyFrom](#copyfrom)|Метод копирования, который задает разделитель элементов переменные из другого объекта.|  
|[CMFCRibbonSeparator::GetRegularSize](#getregularsize)|Возвращает размер разделителя.|  
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|Указывает, является ли разделитель.|  
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|Указывает, является ли это позиции табуляции.|  
|[CMFCRibbonSeparator::OnDraw](#ondraw)|Вызывается системой для рисования разделителя на ленте или панели инструментов быстрого доступа.|  
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|Вызывается системой для отрисовки в качестве разделителя в **команды** списка.|  
  
## <a name="remarks"></a>Примечания  
 Разделитель ленты — вертикальной или горизонтальной линией, логически разделяет элементы ленты. Разделитель можно рисовать на элемент управления ленты, в меню основного приложения, строки состояния ленты и панель быстрого доступа.  
  
 Необходимо использовать разделитель в приложении, создать новый объект и добавьте его в меню основного приложения, как показано ниже:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```  
Вызовите [CMFCRibbonPanel::AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) добавление панелей ленты в качестве разделителей. Выделение и добавлены внутренним образом в разделители `AddSeparator` метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxbaseribbonelement.h  
  
##  <a name="addtolistbox"></a>CMFCRibbonSeparator::AddToListBox  
 Добавляет разделитель для **команды** списка в **Настройка** диалоговое окно.  
  
```  
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,  
    BOOL bDeep);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pWndListBox`  
 Указатель на **команды** списка, куда добавляется разделителя.  
  
 [in] `bDeep`  
 Не обрабатывается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Отсчитываемый от нуля индекс строки, в поле со списком, определяемое `pWndListBox`.  
  
##  <a name="cmfcribbonseparator"></a>CMFCRibbonSeparator::CMFCRibbonSeparator  
 Создает объект `CMFCRibbonSeparator`.  
  
```  
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bIsHoriz`  
 Если `TRUE`, горизонтальный разделитель; Если `FALSE`, вертикальный разделитель.  
  
### <a name="remarks"></a>Примечания  
 В меню приложения используются горизонтальные разделители. В панели инструментов используются вертикальные разделители.  
  
### <a name="example"></a>Пример  
 Следующий пример демонстрирует создание объекта `CMFCRibbonSeparator` класса.  
  
 [!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]  
  
##  <a name="copyfrom"></a>CMFCRibbonSeparator::CopyFrom  
 Метод копирования, который задает разделитель элементов переменные из другого объекта.  
  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `Src`  
 Исходный элемент ленты для копирования из.  
  
##  <a name="getregularsize"></a>CMFCRibbonSeparator::GetRegularSize  
 Возвращает размер разделителя.  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на содержимое устройства.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Размер разделителя в контексте данного устройства.  
  
##  <a name="isseparator"></a>CMFCRibbonSeparator::IsSeparator  
 Указывает, является ли разделитель.  
  
```  
virtual BOOL IsSeparator() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `TRUE` к этому классу.  
  
##  <a name="istabstop"></a>CMFCRibbonSeparator::IsTabStop  
 Указывает, является ли это позиции табуляции.  
  
```  
virtual BOOL IsTabStop() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда `FALSE` к этому классу.  
  
### <a name="remarks"></a>Примечания  
 Разделитель ленты не табуляции.  
  
##  <a name="ondraw"></a>CMFCRibbonSeparator::OnDraw  
 Вызывается системой для рисования разделителя на ленте или панели инструментов быстрого доступа.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
##  <a name="ondrawonlist"></a>CMFCRibbonSeparator::OnDrawOnList  
 Вызывается системой для отрисовки в качестве разделителя в **команды** списка.  
  
```  
virtual void OnDrawOnList(
    CDC* pDC,  
    CString strText,  
    int nTextOffset,  
    CRect rect,  
    BOOL bIsSelected,  
    BOOL bHighlighted);
```  
  
### <a name="parameters"></a>Параметры  
  
|||  
|-|-|  
|Параметр|Описание:|  
|[in] `pDC`|Указатель на контекст устройства.|  
|[in] `strText`|Текст, отображаемый в списке.|  
|[in] `nTextOffset`|Интервал между текстом и левой стороны обрамляющего прямоугольника.|  
|[in] `rect`|Указывает ограничивающий прямоугольник.|  
|[in] `bIsSelected`|Не обрабатывается.|  
|[in] `bHighlighted`|Не обрабатывается.|  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)
