---
title: Использование операторов CArchive &lt; &lt; и &gt; &gt;
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 5029227078ac0af9ebdd0c74522a7b0ae8ea4d42
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228522"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Использование операторов CArchive &lt; &lt; и &gt; &gt;

`CArchive`предоставляет <\< and >> операторы для записи и чтения простых типов данных, а также `CObject` для файлов и из них.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Сохранение объекта в файле с помощью архива

1. В следующем примере показано, как сохранить объект в файле с помощью архива:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Загрузка объекта из значения, сохраненного ранее в файле

1. В следующем примере показано, как загрузить объект из значения, ранее сохраненного в файле:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Обычно хранение и загрузка данных в файл и из него осуществляется через архив в `Serialize` функциях `CObject` , производных от класса, которые должны быть объявлены с помощью макроса DECLARE_SERIALIZE. Ссылка на `CArchive` объект передается в `Serialize` функцию. Чтобы `IsLoading` `CArchive` определить, `Serialize` была ли вызвана функция для загрузки данных из файла или сохранения данных в файл, вызывается функция объекта.

`Serialize`Функция сериализуемого `CObject` класса, производного от, обычно имеет следующую форму:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Приведенный выше шаблон кода точно такой же, как и один помощью мастера, создаваемый для `Serialize` функции документа (класс, производный от `CDocument` ). Этот шаблон кода помогает написать код, который проще просматривать, поскольку код хранения и код загрузки всегда должны быть параллельными, как показано в следующем примере:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Библиотека определяет **<\<** and **>>** операторы для `CArchive` первого операнда и следующие типы данных и типы классов в качестве второго операнда:

||||
|-|-|-|
|`CObject*`|**Размер** и`CSize`|**`float`**|
|**СЛОВАМ**|`CString`|**Point** и`CPoint`|
|`DWORD`|**ДВУХБАЙТОВЫХ**|`RECT` и `CRect`|
|**Double**|**ПОДДЕРЖИВАЕМ**|`CTime` и `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
> Хранение и загрузка `CObject` с помощью архива требует дополнительного рассмотрения. Дополнительные сведения см. в разделе [Хранение и загрузка CObjects через Архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Операторы **<\<** and **> > CArchive** всегда возвращают ссылку на `CArchive` объект, который является первым операндом. Это позволяет создавать цепочки операторов, как показано ниже:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>См. также статью

[Сериализация: сериализация объекта](../mfc/serialization-serializing-an-object.md)
