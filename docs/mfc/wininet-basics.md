---
title: Основные сведения о WinInet | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OnStatusCallback method [MFC]
- WinInet classes [MFC], displaying progress
- WinInet classes [MFC], about WinInet classes
ms.assetid: 665de5ac-e80d-427d-8d91-2ae466885940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38506d0b25918bbc9d70ec1801971b070d620bf9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="wininet-basics"></a>Основные сведения о WinInet
WinInet можно использовать для добавления поддержки FTP для загрузки и отправки файлов из приложения. Можно переопределить [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) и использовать `dwContext` параметр для предоставления сведений о ходе выполнения для пользователей, как поиск и загрузка файлов.  
  
 В этой статье рассматриваются следующие вопросы:  
  
-   [Создание очень простого браузера](#_core_create_a_very_simple_browser)  
  
-   [Загрузка веб-страницы](#_core_download_a_web_page)  
  
-   [FTP-файла](#_core_ftp_a_file)  
  
-   [Получить каталога Gopher](#_core_retrieve_a_gopher_directory)  
  
-   [Отображение сведений о ходе выполнения передачи файлов](#_core_display_progress_information_while_transferring_files)  
  
 Отрывки кода ниже показано, как создать простой браузера, загрузки веб-страницы, FTP файл и найдите файл gopher. Они не предназначены как полные примеры и не содержат обработки исключений.  
  
 Дополнительные сведения о WinInet см. в разделе [расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md).  
  
##  <a name="_core_create_a_very_simple_browser"></a> Создание очень простого браузера  
 [!code-cpp[NVC_MFCWinInet#1](../mfc/codesnippet/cpp/wininet-basics_1.cpp)]  
  
##  <a name="_core_download_a_web_page"></a> Загрузка веб-страницы  
 [!code-cpp[NVC_MFCWinInet#2](../mfc/codesnippet/cpp/wininet-basics_2.cpp)]  
  
##  <a name="_core_ftp_a_file"></a> FTP-файла  
 [!code-cpp[NVC_MFCWinInet#3](../mfc/codesnippet/cpp/wininet-basics_3.cpp)]  
  
##  <a name="_core_retrieve_a_gopher_directory"></a> Получить каталога Gopher  
 [!code-cpp[NVC_MFCWinInet#4](../mfc/codesnippet/cpp/wininet-basics_4.cpp)]  
  
## <a name="use-onstatuscallback"></a>Использовать OnStatusCallback  
 При использовании WinInet-классы, можно использовать [OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) членом приложения [CInternetSession](../mfc/reference/cinternetsession-class.md) объекта для получения сведений о состоянии. Если вы наследуете собственные `CInternetSession` объекта, переопределите `OnStatusCallback`и включить состояние обратные вызовы, MFC вызывает вашей `OnStatusCallback` функция сведения о ходе выполнения о все действия в этом сеансе Интернета.  
  
 Так как один сеанс может поддерживать несколько подключений (которые по времени их существования может выполнения различных операций distinct), `OnStatusCallback` необходим механизм для идентификации каждого изменения состояния с определенной подключения или транзакции. Этот механизм обеспечивает параметр контекста идентификатор, присвоенный многие из функций-членов в классы поддержки WinInet. Этот параметр всегда имеет тип `DWORD` и всегда имеет имя `dwContext`.  
  
 Контекст, назначенных для определенного объекта Интернет используется только для идентификации объекта приводит в действие `OnStatusCallback` членом `CInternetSession` объекта. Вызов `OnStatusCallback` принимает несколько параметров; эти параметры работают совместно определить приложения, какие прогресса какие транзакции и подключения.  
  
 При создании `CInternetSession` объекта, можно указать `dwContext` параметра конструктора. `CInternetSession` сам не использовать идентификатор контекста; Вместо этого он передает идентификатор контекста на любой **Интернет-соединение**-производных объектов, которые явно не получить ИД контекста собственные. В свою очередь, те `CInternetConnection` объектов будет передавать ИД контекста вдоль `CInternetFile` объекты, они создают, если не указать явно с идентификатором другого контекста. Если, с другой стороны, указать свой собственный идентификатор определенного контекста, объекта и вся работа будет связан с этим идентификатором контекста. Контекст идентификаторы можно использовать для определения, какие сведения о состоянии имеет для вас в вашей `OnStatusCallback` функции.  
  
##  <a name="_core_display_progress_information_while_transferring_files"></a> Отображение сведений о ходе выполнения передачи файлов  
 Например, при написании приложения, которое создает соединение с FTP-сервера для считывания файла, а также подключается к HTTP-серверу, чтобы получить на веб-странице, чтобы иметь `CInternetSession` объекта, двух `CInternetConnection` объектов (одним будет **CFtpSession** и другой **CHttpSession**) и два `CInternetFile` объектов (по одному для каждого соединения). Если вы использовали значения по умолчанию для `dwContext` параметров, то будет невозможно провести различие между `OnStatusCallback` вызовы, которые указывают на ход выполнения для FTP-соединения и вызовы, которые указывают на ход выполнения для HTTP-соединений. При указании `dwContext` идентификатор, который позже можно проверить в `OnStatusCallback`, вы будете знать, какая операция создается обратный вызов.  
  
## <a name="see-also"></a>См. также  
 [Основы программирования для Интернет MFC](../mfc/mfc-internet-programming-basics.md)   
 [Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)

