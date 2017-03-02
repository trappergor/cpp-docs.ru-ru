---
title: "Структура AFX_EXTENSION_MODULE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f2699316266e9cc061fa898c4176e36ae8323b33
ms.lasthandoff: 02/24/2017

---
# <a name="afxextensionmodule-structure"></a>Структура AFX_EXTENSION_MODULE
`AFX_EXTENSION_MODULE` Используется для хранения состояния модуля DLL расширения во время инициализации библиотеки расширения MFC.  
  
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
 Определяет дескриптор модуля DLL настраиваемого ресурса.  
  
 *pFirstSharedClass*  
 Указатель на сведения ( `CRuntimeClass` структуры) о первого класса среды выполнения модуля DLL. Используется для начала список классов среды выполнения.  
  
 *pFirstSharedFactory*  
 Указатель на первый объект фабрики модуля DLL ( `COleObjectFactory` объекта). Используется для начала списка фабрики класса.  
  
## <a name="remarks"></a>Примечания  
 Расширения MFC DLL-библиотеки нужно сделать две вещи в свои `DllMain` функции:  
  
-   Вызов [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1) и проверить возвращаемое значение.  
  
-   Создание **CDynLinkLibrary** объекта, если библиотека DLL будет Экспорт [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объектов или имеет свои собственные настраиваемые ресурсы.  
  
 `AFX_EXTENSION_MODULE` Структура используется для хранения копии состояния модуля DLL, включая копирование объектов классов среды выполнения, которые инициализированы с помощью расширения DLL в рамках конструирования обычный статический объект, перед выполнением расширения `DllMain` вводится. Пример:  
  
 [!code-cpp[NVC_MFC_DLL&#2;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_1.cpp)]  
  
 Сведения о модуле, хранящиеся в `AFX_EXTENSION_MODULE` структуры могут быть скопированы в **CDynLinkLibrary** объекта. Пример:  
  
 [!code-cpp[NVC_MFC_DLL&#5;](../../atl-mfc-shared/codesnippet/cpp/afx-extension-module-structure_2.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxInitExtensionModule](http://msdn.microsoft.com/library/15f0c820-ff34-4da6-8077-79afbbb8dac1)   
 [AfxTermExtensionModule](http://msdn.microsoft.com/library/b64de402-f1e3-4c26-9823-08c07876aaaa)


