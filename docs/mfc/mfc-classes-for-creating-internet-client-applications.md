---
title: Классы MFC для создания клиентских приложений в Интернете
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, WinInet classes
- WinInet classes [MFC], classes
- classes [MFC], MFC
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
ms.assetid: 67d34117-9839-4f4b-8bb8-0e4a9471c606
ms.openlocfilehash: 578fd5b72e6c04610aa862f1a6631895a32a9bfe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358217"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Классы MFC для создания клиентских приложений в Интернете

MFC предоставляет следующие классы и глобальные функции для написания приложений для интернет-клиентов. Отступ указывает на то, что класс происходит от неотвраченного класса над ним. `CGopherFile`и `CHttpFile` вытекают из, `CInternetFile`например. Эти классы и глобальные функции объявлены в AFXINET. H, `CFileFind`за исключением , который объявлен в AFX. H.

## <a name="classes"></a>Классы

- [CInternetSession](../mfc/reference/cinternetsession-class.md)

- [CInternetConnection](../mfc/reference/cinternetconnection-class.md)

  - [CFtpConnection](../mfc/reference/cftpconnection-class.md)

  - [CGopherConnection](../mfc/reference/cgopherconnection-class.md)

  - [CHttpConnection](../mfc/reference/chttpconnection-class.md)

- [CInternetFile](../mfc/reference/cinternetfile-class.md)

  - [CGopherFile](../mfc/reference/cgopherfile-class.md)

  - [CHttpFile](../mfc/reference/chttpfile-class.md)

- [CFileFind](../mfc/reference/cfilefind-class.md)

  - [CFtpFileFind](../mfc/reference/cftpfilefind-class.md)

  - [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md)

- [CGopherLocator](../mfc/reference/cgopherlocator-class.md)

- [CInternetConnection](../mfc/reference/cinternetexception-class.md)

## <a name="global-functions"></a>Глобальные функции

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>См. также раздел

[Расширения Интернета Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Предпосылки для занятий интернет-клиентов](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
