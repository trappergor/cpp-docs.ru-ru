---
title: С помощью CArchive &lt; &lt; и &gt; &gt; операторы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CArchive
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82b729caaa650fde72741497d3f4ab3c131f46ab
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>С помощью CArchive &lt; &lt; и &gt; &gt; операторы
`CArchive` предоставляет <\< и >> операторы для записи и чтения простых типов данных в том числе в `CObject`s, чтобы из файла.  
  
#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Для хранения объекта в файле через архив  
  
1.  Приведенный ниже показано, как сохранить объект в файл с помощью архива:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Для загрузки объекта из значения, ранее сохраненного в файле  
  
1.  В следующем примере показано, как загрузить объект со значением параметра ранее хранятся в файле:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 Обычно, сохранять и загружать данные в файл через архив в и из `Serialize` функции `CObject`-производные классы, которые должны объявлены с **DECLARE_SERIALIZE** макрос. Ссылку на `CArchive` объект передается в ваш `Serialize` функции. Можно вызвать `IsLoading` функция `CArchive` объектом, чтобы определить ли `Serialize` функция была вызвана для загрузки данных из файла или хранения данных в файле.  
  
 `Serialize` Функции сериализуемый `CObject`-производного класса, обычно имеет следующий вид:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 В шаблоне кода выше именно в том же создается мастером приложений для `Serialize` функция документа (класс, производный от **CDocument)**. Этот шаблон кода помогает писать код, который является читабельность, так как код сохранения и загрузки кода всегда должна параллельных, как показано в следующем примере:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 Библиотека определяет **< \<** и **>>** операторов для `CArchive` как первый операнд и следующие типы данных и типы классов в качестве второго операнда :  
  
||||  
|-|-|-|  
|`CObject*`|**РАЗМЕР и CSize**|**float**|  
|**WORD**|`CString`|**ТОЧКА** и `CPoint`|  
|`DWORD`|**BYTE**|`RECT` и `CRect`.|  
|**Double**|**LONG**|`CTime` и `CTimeSpan`.|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  Сохранение и загрузка `CObject`s через архив требует дополнительных рассмотрения. Дополнительные сведения см. в разделе [хранение и загрузка CObjects через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 **CArchive <\<**  и **>>** операторы всегда возвращают ссылку на `CArchive` объект, который является первым операндом. Это позволяет соединять в цепочку операторы, как показано ниже:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

