---
title: "Инициализация OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 014d0679be8a03b60c2e759b36c056b35784be78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ole-initialization"></a>Инициализация OLE
Прежде чем приложение может использовать OLE системные службы, необходимо инициализировать OLE системные библиотеки DLL и убедитесь, что правильная версия библиотеки DLL. **AfxOleInit** функция инициализирует OLE системные библиотеки DLL.  
  
### <a name="ole-initialization"></a>Инициализация OLE  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Инициализирует библиотек OLE.| 
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|Вызовите эту функцию в объект приложения `InitInstance` функции, чтобы включить поддержку для включения элементов управления OLE.| 


## <a name="afxenablecontrolcontainer"></a>AfxEnableControlContainer
Вызовите эту функцию в объект приложения `InitInstance` функции, чтобы включить поддержку для включения элементов управления OLE.  
   
### <a name="syntax"></a>Синтаксис    
```
void AfxEnableControlContainer( );  
```  
   
### <a name="remarks"></a>Примечания  
 Дополнительные сведения об элементах управления OLE (теперь называется элементы управления ActiveX) см. в разделе [разделы элемента управления ActiveX](../mfc-activex-controls.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  

  
##  <a name="afxoleinit"></a>AfxOleInit  
 Инициализирует OLE поддержки для приложения.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если успешно; 0, если инициализация завершается ошибкой, возможно потому, что установлены неверные версии системных DLL OLE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для инициализации OLE поддержка приложения MFC. При вызове этой функции, выполняются следующие действия:  
  
-   Инициализирует библиотеку COM в текущем подразделении вызывающего приложения. Дополнительные сведения см. в разделе [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Создает объект фильтра сообщений реализации [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) интерфейса. Этот фильтр сообщений может осуществляться с помощью вызова [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter).  
  
> [!NOTE]
>  Если **AfxOleInit** вызывается из библиотеки DLL MFC, вызов завершится ошибкой. Произошел сбой, так как функция предполагает, что, если она вызывается из библиотеки DLL, система OLE ранее был инициализирован в вызывающем приложении.  
  
> [!NOTE]
>  Приложения MFC необходимо инициализировать в виде однопотокового подразделения (STA). При вызове метода [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) в ваш `InitInstance` переопределения, укажите `COINIT_APARTMENTTHREADED` (а не `COINIT_MULTITHREADED`). Дополнительные сведения см. в статье PRB: приложение MFC перестает отвечать при инициализации приложения в качестве многопотокового подразделения (828643) в [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
