---
title: С помощью CArchive &lt; &lt; и &gt; &gt; операторы | Документация Майкрософт
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
ms.openlocfilehash: 74660dc2baeff683d35fac8d4b9dda06bdbec22d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061317"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>С помощью CArchive &lt; &lt; и &gt; &gt; операторы

`CArchive` предоставляет <\< и >> операторы для записи и чтения простых типов данных в том числе в `CObject`s, чтобы из файла.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Для хранения объекта в файле через архив

1. В следующем примере показано, как для хранения объекта в файле через архив:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Для загрузки объекта из значения ранее сохраняются в файле

1. Приведенный ниже показано, как загрузить объект со значением параметра ранее сохраняются в файле:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Как правило, сохранять и загружать данные в файл с помощью архива в и из `Serialize` функции `CObject`-производные классы, которые должен был объявлен с помощью макроса DECLARE_SERIALIZE. Ссылку на `CArchive` объект передается в вашей `Serialize` функции. Вы вызываете `IsLoading` функции `CArchive` объектом, чтобы определить ли `Serialize` функция была вызвана для загрузки данных из файла или хранения данных в файл.

`Serialize` Функции сериализуемый `CObject`-производного класса обычно имеет следующий вид:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

В приведенном выше шаблоне кода именно то, как создается мастером приложений для `Serialize` функция документа (класс, производный от `CDocument`). Этот шаблон кода помогает писать код, который проще просмотреть, так как код сохранения и загрузки кода всегда должно быть параллельной, как показано в следующем примере:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Библиотека определяет **< \<** и **>>** операторов для `CArchive` как первый операнд и следующие типы данных и типы классов в качестве второго операнда :

||||
|-|-|-|
|`CObject*`|**РАЗМЕР** и `CSize`|**float**|
|**WORD**|`CString`|**ТОЧКА** и `CPoint`|
|`DWORD`|**BYTE**|`RECT` и `CRect`|
|**Double**|**LONG**|`CTime` и `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  Сохранение и загрузка `CObject`s через архив требует дополнительных соображений. Дополнительные сведения см. в разделе [хранение и загрузка CObjects через архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).

**CArchive <\<**  и **>>** операторы всегда возвращают ссылку на `CArchive` объект, который является первым операндом. Это позволяет объединить в цепочку операторы, как показано ниже:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>См. также

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)

