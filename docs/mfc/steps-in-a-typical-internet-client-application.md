---
title: "Шаги в клиентском приложении обычно Интернета | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ce4f5b91ebd68f13510f887c65927dbe5f84133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-internet-client-application"></a>Шаги для организации типичного клиентского приложения в Интернете
Ниже приведены шаги, которые необходимо выполнять в обычном клиентском приложении Internet.  
  
|Ваша цель|Выполняемые действия|Произведенный эффект|  
|---------------|----------------------|-------------|  
|Начните Интернет-сеанс.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|  
|Задайте параметр запроса Интернет (предел времени ожидания или число повторных попыток, например).|Используйте [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Возвращает значение FALSE, если операция завершилась неудачно.|  
|Создайте функцию обратного вызова для наблюдения за состоянием сеанса.|Используйте [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Устанавливает обратный вызов [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Переопределить `OnStatusCallback` Чтобы создать собственную процедуру обратного вызова.|  
|Подключиться к Интернету сервера, сервер в интрасети или локальный файл.|Используйте [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Выполняет синтаксический анализ URL-адрес и открывает соединение с указанным сервером. Возвращает [CStdioFile](../mfc/reference/cstdiofile-class.md) (Если вы передаете `OpenURL` имя локального файла). Это объект, через который осуществляется доступ к данным, полученного с сервера или файла.|  
|Чтение из файла.|Используйте [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|Считывает указанное число байтов, с помощью буфера указанные вами.|  
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернета.|  
|Завершение сеанса Интернета.|Удалить [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|  
  
## <a name="see-also"></a>См. также  
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Предварительные требования для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)   
 [Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
