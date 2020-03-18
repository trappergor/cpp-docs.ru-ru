---
title: Использование операторов CArchive &lt;&lt; и &gt;&gt;
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 8e175f35f2218341c69571c818711596180df4a6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442174"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Использование операторов CArchive &lt;&lt; и &gt;&gt;

`CArchive` предоставляет <\< и > > операторы для записи и чтения простых типов данных, а также `CObject`s в файл и обратно.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Сохранение объекта в файле с помощью архива

1. В следующем примере показано, как сохранить объект в файле с помощью архива:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Загрузка объекта из значения, сохраненного ранее в файле

1. В следующем примере показано, как загрузить объект из значения, ранее сохраненного в файле:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Обычно хранение и загрузка данных в файл и из него осуществляется с помощью архива в `Serialize`ных функциях классов, производных от `CObject`, которые должны быть объявлены с помощью макроса DECLARE_SERIALIZE. Ссылка на объект `CArchive` передается функции `Serialize`. Вызовите функцию `IsLoading` объекта `CArchive`, чтобы определить, была ли вызвана функция `Serialize` для загрузки данных из файла или сохранения данных в файл.

Функция `Serialize` сериализуемого класса, производного от `CObject`, обычно имеет следующий вид:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Приведенный выше шаблон кода точно такой же, как и один помощью мастера, создаваемый для функции `Serialize` документа (класс, производный от `CDocument`). Этот шаблон кода помогает написать код, который проще просматривать, поскольку код хранения и код загрузки всегда должны быть параллельными, как показано в следующем примере:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Библиотека определяет **<\<** и операторы **>>** для `CArchive` в качестве первого операнда, а также следующие типы данных и типы классов в качестве второго операнда:

||||
|-|-|-|
|`CObject*`|**Размер** и `CSize`|**float**|
|**WORD**|`CString`|**Point** и `CPoint`|
|`DWORD`|**BYTE**|`RECT` и `CRect`|
|**Double**|**LONG**|`CTime` и `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
>  Хранение и загрузка `CObject`с помощью архива требует дополнительного рассмотрения. Дополнительные сведения см. в разделе [Хранение и загрузка CObjects через Архив](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Операторы **CArchive <\<** и **>>** всегда возвращают ссылку на объект `CArchive`, который является первым операндом. Это позволяет создавать цепочки операторов, как показано ниже:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
