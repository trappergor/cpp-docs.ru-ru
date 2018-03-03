---
title: "Шаги в типичного клиентского приложения Gopher | Документы Microsoft"
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
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5108e997336e53434ad33030c0e79be027aa4a98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Шаги для организации типичного клиентского приложения Gopher
Ниже приведены шаги, которые необходимо выполнять в типичного клиентского приложения gopher.  
  
|Ваша цель|Выполняемые действия|Произведенный эффект|  
|---------------|----------------------|-------------|  
|Начните сеанс gopher.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|  
|Подключение к серверу gopher.|Используйте [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Возвращает [CGopherConnection](../mfc/reference/cgopherconnection-class.md) объекта.|  
|Найти первый ресурс в gopher.|Используйте [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile).|Находит первый файл. Возвращает значение FALSE, если файлы не найдены.|  
|Поиск следующего ресурса в gopher.|Используйте [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Находит следующий файл. Возвращает значение FALSE, если файл не найден.|  
|Откройте файл, обнаруженные **FindFile** или `FindNextFile` для чтения.|Получить средство поиска gopher с помощью [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Используйте [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Открывает файл, указанный в указателе. `OpenFile`Возвращает [CGopherFile](../mfc/reference/cgopherfile-class.md) объекта.|  
|Откройте файл, используя указанные вами локатора gopher.|Создание с помощью указателя gopher [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator). Используйте [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Открывает файл, указанный в указателе. `OpenFile`Возвращает [CGopherFile](../mfc/reference/cgopherfile-class.md) объекта.|  
|Чтение из файла.|Используйте [CGopherFile](../mfc/reference/cgopherfile-class.md).|Считывает указанное число байтов, с помощью буфера указанные вами.|  
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса gopher.|Удалить [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Предварительные требования для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
