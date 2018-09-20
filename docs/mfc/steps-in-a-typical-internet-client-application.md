---
title: Шаги в клиентском приложении обычно Интернет | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd3dde01d87fccd1d19d947a1069fa92675e6053
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390346"
---
# <a name="steps-in-a-typical-internet-client-application"></a>Шаги для организации типичного клиентского приложения в Интернете

В следующей таблице представлены действия, необходимо выполнять в типичных клиентских приложений в Интернете.

|Ваша цель|Выполняемые действия|Произведенный эффект|
|---------------|----------------------|-------------|
|Начните сеанс Интернета.|Создание [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Инициализирует WinInet и подключается к серверу.|
|Настроить параметр запроса Интернет (предел времени ожидания или число повторных попыток, например).|Используйте [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|Возвращает значение FALSE, если операция завершилась неудачно.|
|Установите функцию обратного вызова для проверки состояния сеанса.|Используйте [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Задает обратный вызов к [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Переопределить `OnStatusCallback` создать собственную подпрограмму обратного вызова.|
|Соединиться с сервера Интернета, сервер в интрасети или локального файла.|Используйте [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|Выполняет синтаксический анализ URL-адрес и открывает подключение к указанному серверу. Возвращает [CStdioFile](../mfc/reference/cstdiofile-class.md) (при передаче `OpenURL` локальное имя файла). Это объект, через который осуществляется доступ к данным, полученного с сервера или файла.|
|Чтение из файла.|Используйте [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|Считывает указанное число байтов, с помощью буфера указанные вами.|
|Обработка исключений.|Используйте [CInternetException](../mfc/reference/cinternetexception-class.md) класса.|Обрабатывает все общие типы исключений Интернет.|
|Завершите сеанс Интернета.|Избавиться от [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта.|Автоматически очищает открытые дескрипторы файлов и подключений.|

## <a name="see-also"></a>См. также

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Необходимые компоненты для клиентских классов в Интернете](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
