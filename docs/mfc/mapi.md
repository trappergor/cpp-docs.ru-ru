---
title: MAPI | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messaging [MFC], client applications
- enabling applications for MAPI [MFC]
- MAPI support in MFC
- e-mail [MFC], enabling
- mail [MFC], enabling your application
- MAPI, MFC
- enabling applications for mail [MFC]
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1df0d00aa6356fa1741e7f4fc34d8063782da859
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930678"
---
# <a name="mapi"></a>MAPI
Для разработчиков приложений сообщения клиента в этой статье описываются Microsoft программирования интерфейс MAPI (Messaging Application). MFC предоставляет поддержку для подмножества MAPI в классе `CDocument` , но не содержит всей API. Дополнительные сведения см. в разделе [поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md).  
  
 MAPI — это набор функций, которые используются приложениями почту и поддержкой почты для создания, обработки, передачи и хранить почтовые сообщения. Он предоставляет разработчикам приложений, позволяющих определить назначение и содержание почтовых сообщений и обеспечивает гибкость в управление ими хранимых почтовых сообщений. MAPI также предоставляет общий интерфейс, который разработчики приложений могут использовать для создания почту и почтового приложения зависит от базовой системы обмена сообщениями.  
  
 Клиенты обмена сообщениями предоставляют пользовательского интерфейса для взаимодействия с Microsoft Windows обмена сообщениями системы (WMS). Это взаимодействие обычно включает запрос службы из MAPI-совместимой поставщиков, например хранилищ сообщений и адресные книги.  
  
 Дополнительные сведения о MAPI см. в статьях в руководстве в Win32 MAPI (Messaging) пакета SDK Windows.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md)  
  
## <a name="see-also"></a>См. также  
 [CDocument::OnFileSendMail](../mfc/reference/cdocument-class.md#onfilesendmail)   
 [CDocument::OnUpdateFileSendMail](../mfc/reference/cdocument-class.md#onupdatefilesendmail)   
 [COleDocument::OnFileSendMail](../mfc/reference/coledocument-class.md#onfilesendmail)

