---
title: 'Сериализация: Сериализация объекта | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3439857f14f4c4fa78aa2df3e3da8e5c8941938d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379662"
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

