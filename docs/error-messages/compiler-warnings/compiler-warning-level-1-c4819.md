---
title: "Предупреждение компилятора (уровень 1) C4819 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4819"
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Файл содержит символ, который нельзя отобразить с помощью текущей кодовой страницы \(номер\).Сохраните файл в формате Юникода, чтобы избежать потери данных.  
  
 Ошибка C4819 возникает, когда файл исходного кода ANSI компилируется в системе, кодовая страница которой не может отобразить все символы файла.  
  
 Чтобы устранить ошибку C4819, сохраните файл в формате Юникода.  В Visual Studio выберите **Файл**, **Дополнительные параметры сохранения**.  В диалоговом окне **Дополнительные параметры сохранения** выберите кодировку, способную отобразить все символы файла \(например, UTF\-8\), затем нажмите кнопку **ОК**.