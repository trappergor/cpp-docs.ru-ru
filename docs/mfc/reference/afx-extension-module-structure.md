---
title: "Структура AFX_EXTENSION_MODULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFX_EXTENSION_MODULE
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXTENSION_MODULE structure
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 4bc0dafbc4d09f5c53ff502876da2e250d537882
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="afxextensionmodule-structure"></a>Структура AFX_EXTENSION_MODULE
`AFX_EXTENSION_MODULE` Используется во время инициализации DLL расширения MFC для хранения состояния модуль DLL расширения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct AFX_EXTENSION_MODULE  
{  
    BOOL bInitialized;  
    HMODULE hModule;  
    HMODULE hResource;  
    CRuntimeClass* pFirstSharedClass;  
    COleObjectFactory* pFirstSharedFactory;  
};  
```  
  
#### <a name="parameters"></a>Параметры  
 *bInitialized*  
 **Значение TRUE,** при инициализации модуля DLL с `AfxInitExtensionModule`.  
  
 `hModule`  
 Определяет дескриптор модуля DLL.  
  
 *hResource*  
 Определяет дескриптор DLL настраиваемого модуля ресурсов.  
  
 *pFirstSharedClass*  
 Указатель на сведения ( `CRuntimeClass` структуры) о модуль DLL первого класса среды выполнения. Используется для начала список классов среды выполнения.  
  
 *pFirstSharedFactory*  
 Указатель на первый объект фабрики модуль DLL ( `COleObjectFactory` объекта). Используется для начала списка фабрики класса.  
  
## <a name="remarks"></a>Примечания  
 Расширения MFC библиотеки DLL, необходимо выполнить два действия в их `DllMain` функции:  
  
-   Вызовите [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule) и проверяйте возвращаемое значение.  
  
-   Создание **CDynLinkLibrary** объекта, если библиотека DLL будет экспортироваться [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы.  
  
 `AFX_EXTENSION_MODULE` Структура используется для хранения копии расширения состояния модуля DLL, включая копии объектов класса среды выполнения, которые будут инициализированы с помощью расширения DLL в рамках обычного статического объекта конструирования, перед выполнением `DllMain` вводится. Пример:  
  
 [!code-cpp[NVC_MFC_DLL #2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Сведения о модуле, хранящиеся в `AFX_EXTENSION_MODULE` структуры могут быть скопированы в **CDynLinkLibrary** объекта. Например:  
  
 [!code-cpp[NVC_MFC_DLL #5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)


