---
title: "Класс CUserException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [C++], stopping
- exceptions, throwing
- CUserException class
- errors [C++], trapping
- operations [C++]
- throwing exceptions, stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
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
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8548ffa7ad9032e174d650e210a70a29b0e3f19d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cuserexception-class"></a>Класс CUserException
Создается для остановки операции пользователя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>Примечания  
 Использовать `CUserException` Если вы хотите использовать механизм обработки исключений throw и catch для исключений, связанных с приложением. «Пользователь» в имени класса можно интерпретировать как «пользователей отслеживаем исключительные, что нужно обрабатывать.»  
  
 Объект `CUserException` обычно вызывается после вызова глобальной функции `AfxMessageBox` для уведомления пользователя, не удалось выполнить операцию. При написании обработчика исключений, обработки исключения, специально, поскольку пользователь обычно уже получил уведомление о сбое. В некоторых случаях, платформа создает это исключение. Для вызова `CUserException` самостоятельно, оповещения пользователя, а затем вызовите глобальную функцию `AfxThrowUserException`.  
  
 В следующем примере функция, содержащая операции, которые может завершиться ошибкой оповещает пользователя и выдает `CUserException`. Вызывающая функция перехватывает исключение и обрабатывает ее специально:  
  
 [!code-cpp[NVC_MFCExceptions&#24;](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 Дополнительные сведения об использовании `CUserException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)

