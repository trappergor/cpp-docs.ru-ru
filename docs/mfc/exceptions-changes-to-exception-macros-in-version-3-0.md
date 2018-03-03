---
title: "Исключения: Изменения в макросах исключений в версии 3.0 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 073715c72dfad83490b377b5d55e1169297be1ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>Исключения. Изменения макроса исключений в версии 3.0
Это довольно сложная тема.  
  
 Макросы обработки исключений с MFC версии 3.0 и более поздних, были изменены в использовании исключений C++. В этой статье описано, как эти изменения могут повлиять на поведение существующего кода, использующего макросы.  
  
 В этой статье рассматриваются следующие темы:  
  
-   [Типы исключений и CATCH-макрос](#_core_exception_types_and_the_catch_macro)  
  
-   [Повторное создание исключений](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a>Типы исключений и CATCH-макрос  
 В более ранних версиях MFC **ПЕРЕХВАТЫВАТЬ** макрос использовать сведения о типах времени выполнения MFC для определения типа исключения, определить тип исключения, другими словами, в узле catch. Исключения C++ тем не менее, тип исключения всегда определяется на сайте throw тип объекта исключения, создается исключение. Это приведет к несовместимости в тех редких случаях, когда тип указателя на объект создается отличается от типа созданный объект.  
  
 Вследствие этого различия между MFC версии 3.0 и более ранних версиях, показано в следующем примере:  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 Этот код по-разному функционирует в версии 3.0, так как элемент управления всегда передает первый **перехватывать** блок с соответствующее объявление исключения. Результат выражения throw  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 вызывается как **CException\***, даже если он формируется как **CCustomException**. **ПЕРЕХВАТЫВАТЬ** макрос в MFC версии 2.5 и более ранних использует `CObject::IsKindOf` для проверки типа во время выполнения. Так как выражение  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 имеет значение true, первый блок catch перехватывает это исключение. В версии 3.0, которая использует исключения C++ реализовать множество макросы обработки исключений, соответствует создается второй блок catch `CException`.  
  
 Следующий код является редкой. Обычно появляется при передаче объекта исключения в другую функцию, которая принимает универсальный **CException\***, выполняет обработку «до создания исключения» и наконец, создается исключение.  
  
 Чтобы обойти эту проблему, переместите выражение throw из функции в вызывающий код и исключение фактический тип, известным компилятору во время генерации.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a>Повторное создание исключений  
 Блок catch не может вызывать тот же указатель исключение, оно перехватывается.  
  
 Например, этот код является допустимым в предыдущих версиях, но будет иметь неожиданные результаты с версии 3.0:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 С помощью **THROW** в catch блока нормализует указатель `e` для удаления, так что внешнее catch сайта будет получать недопустимый указатель. Используйте `THROW_LAST` повторное создание `e`.  
  
 Дополнительные сведения см. в разделе [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

