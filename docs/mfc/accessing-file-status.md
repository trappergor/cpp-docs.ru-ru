---
title: "Доступ к состоянию файла | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2ed2ce199c9f29ca4648e13856b0b9c8d43b605b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="accessing-file-status"></a>Доступ к состоянию файла
`CFile`также поддерживает получение состояния файла, является ли файл существует, даты создания и изменения и времени, логический размер и путь.  
  
### <a name="to-get-file-status"></a>Чтобы получить состояние файла  
  
1.  Используйте [CFile](../mfc/reference/cfile-class.md) класс, чтобы получать и задавать сведения о файле. Один полезные приложения заключается в использовании `CFile` статическая функция-член **GetStatus** для определения того, существует ли файл. **GetStatus** возвращает 0, если указанный файл не существует.  
  
 Таким образом, можно использовать результат **GetStatus** для определения, следует ли использовать **CFile::modeCreate** флаг при открытии файла, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 Дополнительные сведения см. в разделе [сериализации](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [Файлы](../mfc/files-in-mfc.md)

