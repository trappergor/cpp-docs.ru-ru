---
title: Сохранение и загрузка CObjects через архив | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe5cc426e3494117bff98577f02178709a2588f3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380732"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Сохранение и загрузка CObjects через архив
Сохранение и загрузка `CObject`s через архив требует дополнительных рассмотрения. В некоторых случаях необходимо вызвать `Serialize` функцию объекта, где `CArchive` объект — это параметр `Serialize` вызова, а не с помощью **< \<** или **>>** оператор `CArchive`. Это важный аспект, необходимо иметь в виду `CArchive` **>>** конструкции оператор `CObject` в памяти, на основе `CRuntimeClass` сведения, написанный в файле до сохранения архива.  
  
 Таким образом, использование `CArchive` **< \<** и **>>** операторы и вызова `Serialize`, зависит от того вы *требуется* загрузке резервной копии для восстановления объекта динамически на основе ранее сохраненный `CRuntimeClass` сведения. Используйте `Serialize` функции в следующих случаях:  
  
-   В процессе десериализации объект точный класс объекта заранее известно.  
  
-   В процессе десериализации объект памяти, выделенной для него уже установлено.  
  
> [!CAUTION]
>  При загрузке объекта с помощью `Serialize` функции, необходимо также сохранить объект с помощью `Serialize` функции. Не сохранять с помощью `CArchive` **<<** оператор и затем загрузки через `Serialize` функции или сохранить с помощью `Serialize` функции, а затем загружать с помощью **CArchive >>** оператор.  
  
 В следующем примере демонстрируется вариантов:  
  
 [!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]  
  
 [!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]  
  
 Таким образом, если сериализуемый класс определяет встроенный **CObjec**t как член должен *не* использовать `CArchive` **< \<** и **>>** операторы для этого объекта, но следует вызывать `Serialize` вместо этого функцию. Кроме того Если сериализуемый класс определяет указатель на `CObject` (или объект, производный от `CObject`) как член, но конструкции этот объект в свой собственный конструктор, вам также следует вызвать `Serialize`.  
  
## <a name="see-also"></a>См. также  
 [Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

