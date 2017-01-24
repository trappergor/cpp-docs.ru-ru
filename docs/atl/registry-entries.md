---
title: "Registry Entries | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "реестр, application IDs"
  - "реестр, ATL services entries"
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Entries
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM появился понятие идентификаторы приложений \(AppIDs\), которые группируют параметры конфигурации для одного или нескольких объектов DCOM в централизованное расположение в реестре.  Указании AppID, указывая его значение в именованном значение AppID под CLSID объекта.  
  
 По умолчанию Библиотека ATL\- созданная служба использует его CLSID, как GUID для своего AppID.  В `HKEY_CLASSES_ROOT\AppID` можно указать записи DCOM\- в XML\-структуру.  Первоначально 2 записей.  
  
-   `LocalService`, со значением, равным имени службы.  Если это значение присутствует, оно используется вместо ключа `LocalServer32` под CLSID.  
  
-   `ServiceParameters`, со значением, равным `–Service`.  Это значение задает параметры, которые будут переданы службе, когда она будет запуститьа.  Обратите внимание, что эти параметры передать в функцию `ServiceMain` службы, не `WinMain`.  
  
 Любой службе DCOM также необходимо создать другой ключ под `HKEY_CLASSES_ROOT\AppID`.  Этот ключ равен имени EXE\-ФАЙЛА и действует как крест\- ссылка, так как он содержит значение AppID, указывающим обратно к записям AppID.  
  
## См. также  
 [Службы](../atl/atl-services.md)