---
title: "Класс CMFCPropertyGridFileProperty | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridFileProperty
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridFileProperty class
- CMFCPropertyGridFileProperty::OnClickButton method
ms.assetid: 2bb8b8b4-47fc-4798-bd5e-dc8ea0b4cd9d
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 56e9d258f5d608b03497632bef84cf73611f2e9a
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridfileproperty-class"></a>Класс CMFCPropertyGridFileProperty
`CMFCPropertyGridFileProperty` Класс поддерживает элемент управления списка свойств, открывается диалоговое окно выбора файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCPropertyGridFileProperty : public CMFCPropertyGridProperty  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty](#cmfcpropertygridfileproperty)|Создает объект `CMFCPropertyGridFileProperty`.|  
|`CMFCPropertyGridFileProperty::~CMFCPropertyGridFileProperty`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCPropertyGridFileProperty::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|`CMFCPropertyGridFileProperty::OnClickButton`|(Переопределяет [CMFCPropertyGridProperty::OnClickButton](../../mfc/reference/cmfcpropertygridproperty-class.md#onclickbutton).)|  
  
### <a name="remarks"></a>Примечания  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)  
  
 [CMFCPropertyGridFileProperty](../../mfc/reference/cmfcpropertygridfileproperty-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxpropertygridctrl.h  
  
##  <a name="a-namecmfcpropertygridfilepropertya--cmfcpropertygridfilepropertycmfcpropertygridfileproperty"></a><a name="cmfcpropertygridfileproperty"></a>CMFCPropertyGridFileProperty::CMFCPropertyGridFileProperty  
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
 `TRUE`Чтобы открыть **открыть файл** диалоговым окном. `FALSE` открыть **сохранить файл** диалоговое окно.  
  
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
 Полный список доступных флагов см. в разделе [OPENFILENAME структуры](https://msdn.microsoft.com/library/ms646839.aspx).  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется создание объекта с помощью конструктора класса `CMFCPropertyGridFileProperty`. Этот пример является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#22;](../../mfc/codesnippet/cpp/cmfcpropertygridfileproperty-class_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)   
 [Класс CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md)

