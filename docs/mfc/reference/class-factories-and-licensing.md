---
title: "Фабрики классов и лицензирования | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- class factories, and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: a8ef7ba19d2337e4e50f34d7cdd528024a1d90aa
ms.lasthandoff: 02/24/2017

---
# <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание
Для создания экземпляра элемента управления OLE, приложение контейнера вызывает функцию-член фабрики класса элемента управления. Так как элемент управления является фактический объект OLE, фабрика классов отвечает за создание экземпляров элемента управления. Каждый класс элементов управления OLE должен иметь фабрики класса.  
  
 Другой важной особенностью элементов управления OLE является способностью принудительно изменять лицензии. Автоматически позволяет внедрять лицензирования во время создания проекта элемента управления. Дополнительные сведения о лицензировании элементов управления см. в статье [элементы управления ActiveX: Лицензирование элементов управления ActiveX](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
 В следующей таблице перечислены несколько функций, используется для объявления и реализации фабрики класса элемента управления и макросы и лицензии элемента управления.  
  
### <a name="class-factories-and-licensing"></a>Фабрики классов и прослушивание  
  
|||  
|-|-|  
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Объявляет класс фабрики для страницы элемента управления или свойства OLE.|  
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Реализует элемент управления `GetClassID` функции и объявляет экземпляр фабрики класса.|  
|[BEGIN_OLEFACTORY](#begin_olefactory)|Начинается объявление любой лицензирования функций.|  
|[END_OLEFACTORY](#end_olefactory)|Завершает объявление любой лицензирования функций.|  
|[AfxVerifyLicFile](#afxverifylicfile)|Проверяет, является ли элемент управления лицензирован для использования на конкретном компьютере.|  
  
##  <a name="a-namedeclareolecreateexa--declareolecreateex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX  
 Объявляет фабрики класса и `GetClassID` функции-члена класса элемента управления.  
  
```   
DECLARE_OLECREATE_EX(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос в файле заголовка класса элемента управления для элемента управления, который не поддерживает лицензирование.  
  
 Обратите внимание, что этот макрос выполняет те же функции, как в следующем примере кода:  
  
 [!code-cpp[NVC_MFCAxCtl&#14;](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameimplementolecreateexa--implementolecreateex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX  
 Реализует фабрику класса элемента управления и [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) функции-члена класса элемента управления.  
  
```   
IMPLEMENT_OLECREATE_EX(
   class_name,   
    external_name,    
    l,   
    w1,   
    w2,   
    b1,   
    b2,   
    b3,   
    b4,   
    b5,   
    b6,   
    b7,
    b8)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса страницы свойств элемента управления.  
  
 *параметр external_name*  
 Имя объекта, приложениям.  
  
 *l, w1, w2, b1, b2, b3, b4, b5, В6 для, b7, b8*  
 Компоненты класса **CLSID**. Дополнительные сведения об этих параметрах см. заметки для [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate).  
  
### <a name="remarks"></a>Примечания  
 Этот макрос должен присутствовать в файле реализации для любого класса элемента управления, который использует `DECLARE_OLECREATE_EX` макрос или `BEGIN_OLEFACTORY` и `END_OLEFACTORY` макросы. Внешнее имя является идентификатором элемента управления OLE, которые доступны для других приложений. Контейнеры использовать это имя для запроса объекта этого класса элемента управления.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-namebeginolefactorya--beginolefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY  
 Начинается объявление фабрики класса в файле заголовка класса элемента управления.  
  
``` 
BEGIN_OLEFACTORY(class_name)  
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Задает имя класса элемента управления, это фабрики класса.  
  
### <a name="remarks"></a>Примечания  
 Объявления класса фабрики лицензирования функции должно начинаться сразу после `BEGIN_OLEFACTORY`.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameendolefactorya--endolefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY  
 Завершает объявление фабрики класса элемента управления.  
  
```  
END_OLEFACTORY(class_name)   
```  
  
### <a name="parameters"></a>Параметры  
 *class_name*  
 Имя класса элемента управления, это фабрики класса.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  
  
##  <a name="a-nameafxverifylicfilea--afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile  
 Убедитесь, что файл лицензии с именем эта функция `pszLicFileName` является допустимым для элемента управления OLE.  
  
```   
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,  
    LPCTSTR  pszLicFileName,  
    LPOLESTR  pszLicFileContents,  
    UINT cch = -1); 
```  
  
### <a name="parameters"></a>Параметры  
 `hInstance`  
 Дескриптор экземпляра библиотеки DLL, связанные с лицензированный элемент управления.  
  
 `pszLicFileName`  
 Указывает символов с завершающим нулем строка, содержащая имя файла лицензии.  
  
 `pszLicFileContents`  
 Указывает последовательность байтов, которое должно соответствовать последовательности, приведены в начале файла лицензии.  
  
 `cch`  
 Число символов в `pszLicFileContents`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если существует файл лицензии и начинается с последовательности знаков в `pszLicFileContents`; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Если `cch` является â €» 1, эта функция использует:  
  
 [!code-cpp[NVC_MFC_Utilities&#36;](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]  

### <a name="requirements"></a>Требования  
  **Заголовок** afxctl.h  

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

