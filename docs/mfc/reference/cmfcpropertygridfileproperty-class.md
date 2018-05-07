---
title: Класс методе CMFCPropertyGridFileProperty | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty
- AFXPROPERTYGRIDCTRL/CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty [MFC], CMFCPropertyGridFileProperty
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2b123b5c473c834e958263edb926ef25103d788
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcpropertygridfileproperty-class"></a>Класс методе CMFCPropertyGridFileProperty
`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, открывается диалоговое окно выбора файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Создает объект `CMFCPropertyGridFileProperty`.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
### <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [Методе CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="cmfcpropertygridfileproperty"></a>  CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
 Создает объект `CMFCPropertyGridFileProperty`.  
  
```  
CMFCPropertyGridFileProperty(
    const CString& strName,  
    BOOL bOpenFileDialog,  
    const CString& strFileName,  
    LPCTSTR lpszDefExt=NULL,  
    DWORD dwFlags=OFN_HIDEREADONLY|OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter=NULL,  
    LPCTSTR lpszDescr=NULL,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `strName`  
 Имя свойства.  
  
 [in] `bOpenFileDialog`  
 `TRUE` Чтобы открыть **открыть файл** диалоговым окном. `FALSE` Открытие **сохранить файл** диалоговое окно.  
  
 [in] `strFileName`  
 Исходное имя файла.  
  
 [in] `lpszDefExt`  
 Строка, содержащая одно или несколько расширений имен файлов. Значение по умолчанию — `NULL`.  
  
 [in] `dwFlags`  
 Флаги диалогового окна. Значение по умолчанию представляет собой битовую комбинацию (OR) флагов `OFN_HIDEREADONLY` и `OFN_OVERWRITEPROMPT`.  
  
 [in] `lpszFilter`  
 Строка, содержащая один или несколько фильтров файлов. Значение по умолчанию — `NULL`.  
  
 [in] `lpszDescr`  
 Описание элемента свойства. Значение по умолчанию — `NULL`.  
  
 [in] `dwData`  
 Данные приложения, связанные с этим элементом свойства. Например, 32-разрядное целое число или указатель на другие данные. Значение по умолчанию — 0.  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
 Полный список доступных флагов см. в разделе [структура OPENFILENAME](https://msdn.microsoft.com/library/ms646839.aspx).  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта с помощью конструктора класса `CMFCPropertyGridFileProperty`. Данный пример является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#22](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)
