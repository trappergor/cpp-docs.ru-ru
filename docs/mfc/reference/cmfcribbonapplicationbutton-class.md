---
title: "Класс cmfcribbonapplicationbutton – | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton
- AFXRIBBONBAR/CMFCRibbonApplicationButton::SetImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonApplicationButton class
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a6fc19c2af854f3cd4ee3dc3a3008abcb4714ba3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonapplicationbutton-class"></a>Класс cmfcribbonapplicationbutton –
Реализует отдельную кнопку, расположенную в левом верхнем углу окна приложения. При нажатии кнопки открывается меню, которое обычно содержит общие команды **Файл** , **Открыть**, **Сохранить**и **Выход**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](#cmfcribbonapplicationbutton)|Создает и инициализирует объект `CMFCRibbonApplicationButton`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCRibbonApplicationButton::CreateObject`|Используется платформой для создания динамического экземпляра этого типа класса.|  
|`CMFCRibbonApplicationButton::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCRibbonApplicationButton::SetImage](#setimage)|Назначение изображения кнопка приложения на ленте.|  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование различных методов в `CMFCRibbonApplicationButton` класса. В примере показано, как назначить изображение кнопки приложения и как задать ее всплывающей подсказкой. Этот фрагмент кода является частью [пример рисования клиента](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#4;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient&#5;](../../mfc/reference/codesnippet/cpp/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [Cmfcribbonapplicationbutton –](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxRibbonBar.h  
  
##  <a name="cmfcribbonapplicationbutton"></a>CMFCRibbonApplicationButton::CMFCRibbonApplicationButton  
 Создает и инициализирует [cmfcribbonapplicationbutton –](../../mfc/reference/cmfcribbonapplicationbutton-class.md) объекта.  
  
```  
CMFCRibbonApplicationButton();  
CMFCRibbonApplicationButton(UINT uiBmpResID);  
  CMFCRibbonApplicationButton(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Параметры  
 `uiBmpResID`  
 Идентификатор ресурса изображения для отображения на кнопке приложения.  
  
 `hBmp`  
 Дескриптор растровое изображение для отображения на кнопке приложения.  
  
### <a name="remarks"></a>Примечания  
 Кнопка приложения на ленте имеет отдельную кнопку, расположенный в левом верхнем углу окна приложения. Когда пользователь нажимает эту кнопку, программа открывает меню, которое обычно содержит общие **файл** команд, таких как **откройте**, **Сохранить**, и **выхода**.  
  
##  <a name="setimage"></a>CMFCRibbonApplicationButton::SetImage  
 Назначает изображение кнопки приложения.  
  
```  
void SetImage(UINT uiBmpResID);  
void SetImage(HBITMAP hBmp);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `uiBmpResID`  
 Идентификатор ресурса изображения для отображения на кнопке приложения.  
  
 [in] `hBmp`  
 Дескриптор растровое изображение для отображения на кнопке приложения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы назначить новый образ кнопка приложения на ленте после создания кнопки. Кнопка приложения находится в левом верхнем углу окна приложения.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

