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
ms.openlocfilehash: d65a2e8b373f26fe928e4c3e7c0193aec4edf2d6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618036"
---
# <a name="mfc-classes-for-creating-internet-client-applications"></a>Классы MFC для создания клиентских приложений в Интернете

MFC предоставляет следующие классы и глобальные функции для написания клиентских интернет приложений. Отступ указывает, что класс является производным от класса, не являющегося отступом над ним. `CGopherFile`и `CHttpFile` являются производными от `CInternetFile` , например. Эти классы и глобальные функции объявляются в АФКСИНЕТ. H, за исключением `CFileFind` , которое объявлено в AFX. Высоты.

## <a name="classes"></a>Классы

- [CInternetSession](reference/cinternetsession-class.md)

- [CInternetConnection](reference/cinternetconnection-class.md)

  - [CFtpConnection](reference/cftpconnection-class.md)

  - [CGopherConnection](reference/cgopherconnection-class.md)

  - [CHttpConnection](reference/chttpconnection-class.md)

- [CInternetFile](reference/cinternetfile-class.md)

  - [CGopherFile](reference/cgopherfile-class.md)

  - [CHttpFile](reference/chttpfile-class.md)

- [CFileFind](reference/cfilefind-class.md)

  - [CFtpFileFind](reference/cftpfilefind-class.md)

  - [CGopherFileFind](reference/cgopherfilefind-class.md)

- [CGopherLocator](reference/cgopherlocator-class.md)

- [CInternetConnection](reference/cinternetexception-class.md)

## <a name="global-functions"></a>Глобальные функции

- [AfxParseURL](reference/internet-url-parsing-globals.md#afxparseurl)

- [AfxGetInternetHandleType](reference/internet-url-parsing-globals.md#afxgetinternethandletype)

- [AfxThrowInternetException](reference/internet-url-parsing-globals.md#afxthrowinternetexception)

## <a name="see-also"></a>См. также раздел

[Расширения Интернета Win32 (WinInet)](win32-internet-extensions-wininet.md)<br/>
[Необходимые условия для клиентских классов Интернета](prerequisites-for-internet-client-classes.md)<br/>
[Создание клиентских приложений в Интернете с использованием классов MFC WinInet](writing-an-internet-client-application-using-mfc-wininet-classes.md)
