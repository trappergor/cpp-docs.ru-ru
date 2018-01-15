---
title: "Структура AFX_EXTENSION_MODULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AFX_EXTENSION_MODULE
dev_langs: C++
helpviewer_keywords: AFX_EXTENSION_MODULE structure [MFC]
ms.assetid: b85a989c-d0c5-4b28-b53c-dad45b75704e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4ac896fb16aa3c338cadd6273e226eebe986ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="afxextensionmodule-structure"></a>Структура AFX_EXTENSION_MODULE
`AFX_EXTENSION_MODULE` Используется во время инициализации DLL расширения MFC для хранения состояния модуль DLL расширения MFC.  
  
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
  
 `AFX_EXTENSION_MODULE` Структура используется для хранения копии расширения MFC DLL модуля состоянии, включая копии объектов класса среды выполнения, которые будут инициализированы с DLL расширений MFC как часть построения обычного статического объекта перед выполнением `DllMain` — введено. Пример:  
  
 [!code-cpp[NVC_MFC_DLL#2](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Сведения о модуле, хранящиеся в `AFX_EXTENSION_MODULE` структуры могут быть скопированы в **CDynLinkLibrary** объекта. Пример:  
  
 [!code-cpp[NVC_MFC_DLL#5](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](extension-dll-macros.md#afxinitextensionmodule)   
 [AfxTermExtensionModule](extension-dll-macros.md#afxtermextensionmodule)

