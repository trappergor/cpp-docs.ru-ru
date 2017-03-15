---
title: "Инициализация OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
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
ms.openlocfilehash: 5c2d8a1552b8cd546b7e22683fe9f73bbc54df5c
ms.lasthandoff: 02/24/2017

---
# <a name="ole-initialization"></a>Инициализация OLE
Прежде чем приложение может использовать OLE системных служб, необходимо инициализировать OLE системные библиотеки DLL и убедитесь, что правильная версия библиотеки DLL. **AfxOleInit** функция инициализирует OLE системные библиотеки DLL.  
  
### <a name="ole-initialization"></a>Инициализация OLE  
  
|||  
|-|-|  
|[AfxOleInit](#afxoleinit)|Инициализирует библиотек OLE.|  
  
##  <a name="a-nameafxoleinita--afxoleinit"></a><a name="afxoleinit"></a>AfxOleInit  
 Инициализирует OLE поддержку для приложения.  
  
``` 
BOOL AFXAPI AfxOleInit(); 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если выполнено успешно; 0, если инициализация не удается, возможно из-за неправильных версий системные OLE DLLs установлены.  
  
### <a name="remarks"></a>Примечания  
 Эта функция вызывается для инициализации OLE поддержку в приложении MFC. При вызове этой функции, выполняются следующие действия.  
  
-   Инициализирует библиотеку COM в текущем подразделении вызывающего приложения. Дополнительные сведения см. в разделе [OleInitialize](http://msdn.microsoft.com/library/windows/desktop/ms690134).  
  
-   Создает объект фильтра сообщения реализация [IMessageFilter](http://msdn.microsoft.com/library/windows/desktop/ms693740) интерфейса. Этот фильтр сообщений может осуществляться с помощью вызова [AfxOleGetMessageFilter](http://msdn.microsoft.com/library/36cca011-4775-4086-b471-5557a87b266c).  
  
> [!NOTE]
>  Если **AfxOleInit** вызывается из библиотеки DLL MFC, вызов завершится со сбоем. Сбой происходит, поскольку функция предполагает, что, если он вызывается из библиотеки DLL, система OLE ранее был инициализирован в вызывающем приложении.  
  
> [!NOTE]
>  Приложения MFC необходимо инициализировать в виде однопотокового подразделения (STA). При вызове метода [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) в ваш `InitInstance` переопределения, укажите `COINIT_APARTMENTTHREADED` (а не `COINIT_MULTITHREADED`). Дополнительные сведения см. в разделе PRB: приложение MFC перестает отвечать при инициализации приложения в качестве многопоточного подразделения (828643) в [http://support.microsoft.com/default.aspxscid=kb;en-us;828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643).  

### <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

