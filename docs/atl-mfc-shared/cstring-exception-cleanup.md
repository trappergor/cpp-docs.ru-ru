---
title: Очистка исключений CString | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d18d10d517a6c5b0d075a7fb0ed113448625b698
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355510"
---
# <a name="cstring-exception-cleanup"></a>Очистка исключений CString
В предыдущих версий MFC, было важные Очистить [CString](../atl-mfc-shared/reference/cstringt-class.md) объекты после использования. С MFC версии 3.0 и более поздних явная очистка не требуется.  
  
 В списке исключений C++, MFC использует механизм обработки у вас беспокоиться о очистки после исключения. Описание того, как C++ «освобождает» стек после исключение будет перехвачено см. в разделе [try, catch и throw-операторы](../cpp/try-throw-and-catch-statements-cpp.md). Даже при использовании MFC **ПОВТОРИТЕ**/**ПЕРЕХВАТЫВАТЬ** макросы вместо ключевые слова C++ **повторите** и **перехватывать**, MFC использует C++ механизм исключений внизу, поэтому вы по-прежнему не обязательно должны явно очистить.  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

