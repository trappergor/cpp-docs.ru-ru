---
title: Очистка исключений CString | Документация Майкрософт
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
ms.openlocfilehash: 656739ad000612f130f5cdfb1a53a6de2d67c4c8
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761372"
---
# <a name="cstring-exception-cleanup"></a>Очистка исключений CString

В предыдущих версиях MFC, было важно Очистить [CString](../atl-mfc-shared/reference/cstringt-class.md) объекты после использования. С MFC версии 3.0 и более поздних явная очистка больше не требуется.

В разделе, MFC теперь использует механизм обработки исключений языка C++ у вас нет беспокоиться об очистке после исключения. Описание того, как C++ «освобождает» стек после исключение перехватывается, см. в разделе [try, catch и throw инструкций](../cpp/try-throw-and-catch-statements-cpp.md). Даже если вы используете MFC **попробуйте**/**CATCH** макросов вместо ключевые слова C++ **попробуйте** и **catch**, MFC использует C++ механизм исключений под, поэтому вам по-прежнему не обязательно должны явно очистить.

## <a name="see-also"></a>См. также

[Строки (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
[Обработка исключений](../mfc/exception-handling-in-mfc.md)

