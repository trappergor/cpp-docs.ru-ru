---
title: "MAPI | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "электронная почта, включение"
  - "включение приложений для почты"
  - "включение приложений для MAPI"
  - "почта, включение приложения"
  - "поддержка MAPI в MFC"
  - "MAPI, MFC - библиотека"
  - "обмен сообщениями, клиентские приложения"
ms.assetid: 193449f7-b131-4ab0-9301-8d4f6cd1e7c4
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MAPI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе описываются интерфейс MAPI \(MAPI\) Майкрософт для разработчиков приложений сообщения клиента.  Поддержка MFC предоставляет для подмножества MAPI в классе **CDocument**, но не инкапсулирует все API.  Дополнительные сведения см. в разделе [Поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md).  
  
 MAPI набор функций, которые позволяют Почта\- и Почта\- приложении приложений для создания, обработки передачи и сохранять почтовые сообщения.  Это дает разработчикам приложения средства, чтобы определить назначение и содержимое почтовых сообщений и дает им гибкость их в элементе управления, хранимыми в почтовых сообщений.  MAPI также предоставляет общий интерфейс, который разработчики приложения могут использовать для создания Почта\- enabled и Почта\- информации об электропитании не зависит от приложений базовой системы обмена сообщениями.  
  
 Клиенты, которая моделирует передающие предоставляют интерфейс для взаимодействия с системой обмена сообщениями \(WMS\) Microsoft Windows.  Взаимодействие обычно включает запрос службы из MAPI\- совместимых поставщиков, например сообщение хранится и относительной адресной книги.  
  
 Дополнительные сведения о MAPI см. в руководстве статьи в буфер обмена сообщениями Win32 \(MAPI\) [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Содержание  
 [Поддержка MAPI в MFC](../mfc/mapi-support-in-mfc.md)  
  
## См. также  
 [CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)   
 [CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)   
 [COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)