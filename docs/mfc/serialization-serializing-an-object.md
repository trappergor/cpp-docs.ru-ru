---
title: "Сериализация: Сериализация объекта | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37e688a3619cd203e61997999a9b7eb7651d73fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-serializing-an-object"></a>Сериализация. Сериализация объекта
Статья [сериализации: создание сериализуемого класса](../mfc/serialization-making-a-serializable-class.md) показано, как сделать класс сериализуемым. При наличии сериализуемого класса можно сериализовать объекты этого класса и обратно в файл с помощью [CArchive](../mfc/reference/carchive-class.md) объекта. В этой статье описываются:  
  
-   [Какие объект CArchive](../mfc/what-is-a-carchive-object.md).  
  
-   [Два способа создания CArchive](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [Как использовать CArchive <\< и >> операторы](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [Сохранение и загрузка CObjects через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Можно позволить framework явно создать архив сериализуемые документа или `CArchive` объекта самостоятельно. Можно передавать данные между файлом и сериализуемый объект с помощью <\< и >> операторов для `CArchive` или, в некоторых случаях путем вызова `Serialize` функция `CObject`-производного класса.  
  
## <a name="see-also"></a>См. также  
 [Сериализация](../mfc/serialization-in-mfc.md)

