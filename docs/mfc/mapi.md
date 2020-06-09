---
title: MAPI
ms.date: 11/04/2016
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
ms.openlocfilehash: 0008a2bc433401f3e048b6f5a92cded88114d08e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625555"
---
# <a name="mapi"></a>MAPI

В этой статье описывается прикладной программный интерфейс (MAPI) Microsoft Messaging для разработчиков клиентских сообщений. MFC предоставляет поддержку для подмножества MAPI в классе `CDocument` , но не инкапсулирует весь API. Дополнительные сведения см. [в разделе Поддержка MAPI в MFC](mapi-support-in-mfc.md).

MAPI — это набор функций, которые приложения с поддержкой электронной почты и электронной почты используют для создания, обработки, перемещения и хранения почтовых сообщений. Он предоставляет разработчикам приложений средства для определения назначения и содержимого сообщений электронной почты, а также обеспечивает гибкость управления сохраненными почтовыми сообщениями. MAPI также предоставляет общий интерфейс, который разработчики приложений могут использовать для создания приложений с поддержкой почты и электронной почтой независимо от базовой системы обмена сообщениями.

Клиенты обмена сообщениями предоставляют человеческий интерфейс для взаимодействия с системой обмена сообщениями Microsoft Windows (WMS). Это взаимодействие обычно включает в себя запросы служб от поставщиков, соответствующих MAPI, таких как хранилища сообщений и адресные книги.

Дополнительные сведения о MAPI см. в статьях руководства по обмену сообщениями Win32 (MAPI) Windows SDK.

## <a name="in-this-section"></a>В этом разделе

[Поддержка MAPI в MFC](mapi-support-in-mfc.md)

## <a name="see-also"></a>См. также раздел

[CDocument:: Онфилесендмаил](reference/cdocument-class.md#onfilesendmail)<br/>
[CDocument:: Онупдатефилесендмаил](reference/cdocument-class.md#onupdatefilesendmail)<br/>
[Коледокумент:: Онфилесендмаил](reference/coledocument-class.md#onfilesendmail)
