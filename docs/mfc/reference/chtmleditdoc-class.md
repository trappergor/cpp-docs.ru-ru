---
title: "Класс CHtmlEditDoc | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
dev_langs: C++
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1e60c3b175346268b2c6b755786adbd8eb86467
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="chtmleditdoc-class"></a>Класс CHtmlEditDoc
С [CHtmlEditView](../../mfc/reference/chtmleditview-class.md), предоставляет функции платформы редактирования WebBrowser в контексте архитектуры представления документов MFC.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CHtmlEditDoc : public CDocument  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|Создает объект `CHtmlEditDoc`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHtmlEditDoc::GetView](#getview)|Извлекает `CHtmlEditView` объект присоединен к этому документу.|  
|[CHtmlEditDoc::IsModified](#ismodified)|Возвращает значение, показывающее, содержит ли элемент управления WebBrowser связанного представления документ, который был изменен пользователем.|  
|[CHtmlEditDoc::OpenURL](#openurl)|Открытие URL-адреса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `CHtmlEditDoc`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxhtml.h  
  
##  <a name="chtmleditdoc"></a>CHtmlEditDoc::CHtmlEditDoc  
 Создает **CHtmlEditDoc** объекта.  
  
```  
CHtmlEditDoc();
```  
  
##  <a name="getview"></a>CHtmlEditDoc::GetView  
 Извлекает [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) объект присоединен к этому документу.  
  
```  
virtual CHtmlEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на документ **CHtmlEditView** объекта.  
  
##  <a name="ismodified"></a>CHtmlEditDoc::IsModified  
 Возвращает значение, показывающее, содержит ли элемент управления WebBrowser связанного представления документ, который был изменен пользователем.  
  
```  
virtual BOOL IsModified();
```  
  
##  <a name="openurl"></a>CHtmlEditDoc::OpenURL  
 Открытие URL-адреса.  
  
```  
virtual BOOL OpenURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszURL`  
 URL-адрес, чтобы открыть.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при успешном выполнении **FALSE** при сбое.  
  
## <a name="see-also"></a>См. также  
 [Образец HTMLEdit](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)

