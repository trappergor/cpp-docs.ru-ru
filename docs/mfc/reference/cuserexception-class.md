---
title: "Класс CUserException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CUserException
dev_langs: C++
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f88b9f7fb64697061df1e6d32f51a7c88c7e1be6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cuserexception-class"></a>Класс CUserException
Создается для остановки операции пользователя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Примечания  
 Использовать `CUserException` при необходимости использовать механизм обработки исключений throw и catch для исключений, связанных с приложением. «Пользователь» в имени класса можно интерпретировать как «Мой пользователя не то, что исключительные мне нужно обрабатывать.»  
  
 Объект `CUserException` обычно вызывается после вызова глобальной функции `AfxMessageBox` уведомлять пользователя, который не удалось выполнить операцию. При написании обработчика исключений, обработки исключения, специально, поскольку пользователь обычно уже получил уведомление о сбое. Платформа создает это исключение в некоторых случаях. Для вызова `CUserException` самостоятельно, оповещения пользователя, а затем вызовите глобальную функцию `AfxThrowUserException`.  
  
 В следующем примере функция, содержащая операции, которые может завершиться ошибкой предупреждает пользователя и возникает исключение `CUserException`. Вызывающая функция перехватывает это исключение и обрабатывает ее специально:  
  
 [!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Дополнительные сведения об использовании `CUserException`, см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CException](../../mfc/reference/cexception-class.md)
