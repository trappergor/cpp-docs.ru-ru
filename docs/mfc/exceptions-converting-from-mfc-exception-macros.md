---
title: 'Исключения: Преобразование из макросов исключений MFC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8953cc28e35974f7a2a63754533ffd851ca62a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>Исключения. Преобразование из макроса исключений MFC
Это довольно сложная тема.  
  
 В этой статье объясняется, как преобразовать существующий код, написанный с макросами Microsoft Foundation Class — **ПОВТОРИТЕ**, **ПЕРЕХВАТЫВАТЬ**, **THROW**и так далее — чтобы использовать обработку исключений C++ ключевые слова **повторите**, **перехватывать**, и `throw`. Ниже приведен список разделов.  
  
-   [Преимущества преобразования](#_core_advantages_of_converting)  
  
-   [Преобразование кода с помощью макроса исключений, чтобы использовать исключения C++](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> Преимущества преобразования  
 Вы, скорее всего, не обязательно для преобразования существующего кода, несмотря на то, что следует учитывать различия между реализациями макрос с MFC версии 3.0 и реализации в более ранних версиях. Эти различия и последующие изменения в поведении кода обсуждаются в [исключения: изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
 Основные преимущества преобразования являются:  
  
-   Чтобы немного меньше компилирует код, который использует ключевые слова обработки исключений C++. Exe-ФАЙЛ или. БИБЛИОТЕКИ DLL.  
  
-   Ключевые слова обработки исключений C++ являются более универсальными: они могут обрабатывать исключения любого типа данных, который может быть скопирован (`int`, **float**, `char`и так далее), тогда как макросы обработки исключений только класса `CException` и классов, производных от него.  
  
 Основное различие между макросами и ключевые слова является, кода с помощью макросов «автоматически» удаляет перехваченное исключение, когда исключение выходит из области. Код с помощью ключевых слов не так, поэтому необходимо явно удалить перехваченного исключения. Дополнительные сведения см. в статье [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Другое отличие состоит в синтаксис. Синтаксис ключевых слов и макросы отличается в трех аспектах:  
  
1.  Макрос аргументы и объявлениях исключений:  
  
     Объект **ПЕРЕХВАТЫВАТЬ** вызов макроса имеет следующий синтаксис:  
  
     **CATCH (** *exception_class*, *exception_object_pointer_name* **)**  
  
     Обратите внимание, запятая между имя класса и имя указатель объекта.  
  
     Объявления исключения для **перехватывать** ключевое слово используется следующий синтаксис:  
  
     **catch (** *exception_type* *exception_name ***)**  
  
     Этот оператор объявления исключения указывает тип исключения catch блока дескрипторов.  
  
2.  Разграничение блоки catch:  
  
     С макросами **ПЕРЕХВАТЫВАТЬ** (с аргументов), начинаются первого блока catch; `AND_CATCH` макроса начинается блоках catch последующих и `END_CATCH` макрос останавливает последовательность блоков catch.  
  
     С помощью ключевых слов **перехватывать** каждый блок catch начинается ключевое слово (с объявлениями исключение). Нет не аналогом `END_CATCH` макрос; catch блока заканчивается его закрывающей фигурной скобки.  
  
3.  Выражение throw:  
  
     Используйте макросы `THROW_LAST` повторное создание текущее исключение. `throw` Ключевое слово без аргумента имеет тот же эффект.  
  
##  <a name="_core_doing_the_conversion"></a> Это преобразование  
  
#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>Для преобразования кода с использованием макросов использовать ключевые слова обработки исключений C++  
  
1.  Найдите все вхождения макросов MFC **ПОВТОРИТЕ**, **ПЕРЕХВАТЫВАТЬ**, `AND_CATCH`, `END_CATCH`, **THROW**, и `THROW_LAST`.  
  
2.  Замените или удалите все вхождения следующие макросы:  
  
     **ПОВТОРИТЕ** (замените ее строкой **повторите**)  
  
     **CATCH** (замените ее строкой **перехватывать**)  
  
     `AND_CATCH` (Замените ее строкой **перехватывать**)  
  
     `END_CATCH` (Удалить)  
  
     **ИСКЛЮЧЕНИЕ** (замените ее строкой `throw`)  
  
     `THROW_LAST` (Замените ее строкой `throw`)  
  
3.  Измените аргументов макроса так, чтобы они формируют исключение допустимые объявления.  
  
     Например изменение  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     в  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  Измените код в блоках catch, чтобы он удаляет объекты исключений при необходимости. Дополнительные сведения см. в статье [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Ниже приведен пример кода обработки исключений, использование макросов исключений MFC. Обратите внимание, что, так как в следующем примере кода свойство использует макросы, исключение `e` будет автоматически удалена:  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 В коде, в следующем примере используются ключевые слова исключений C++, поэтому исключения должны быть явно удалены:  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 Дополнительные сведения см. в разделе [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

