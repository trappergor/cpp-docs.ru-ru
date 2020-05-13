---
title: Использование CArchive &lt; &lt; &gt; &gt; и операторов
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], loading from previously stored values
- CArchive class [MFC], storing and loading objects
- CArchive class [MFC], operators
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
ms.openlocfilehash: 91ea565867cc0cb3b27ad9d5597037b637cb6544
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368960"
---
# <a name="using-the-carchive-ltlt-and-gtgt-operators"></a>Использование CArchive &lt; &lt; &gt; &gt; и операторов

`CArchive`предоставляет \< <и >> операторов для записи `CObject`и чтения простых типов данных, а также s к и из файла.

#### <a name="to-store-an-object-in-a-file-via-an-archive"></a>Хранение объекта в файле через архив

1. В следующем примере показано, как хранить объект в файле через архив:

   [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_1.cpp)]

#### <a name="to-load-an-object-from-a-value-previously-stored-in-a-file"></a>Загрузка объекта из значения, ранее хранящегося в файле

1. В следующем примере показано, как загрузить объект из значения, ранее хранящегося в файле:

   [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_2.cpp)]

Как правило, вы храните и загружаете `Serialize` данные в и из файла через архив в функциях `CObject`-производных классов, которые вы должны были задекларировать с DECLARE_SERIALIZE макроса. Ссылка на `CArchive` объект передается `Serialize` вашей функции. Вы вызываете функцию `IsLoading` `CArchive` объекта, `Serialize` чтобы определить, была ли функция вызвана для загрузки данных из файла или хранения данных в файл.

Функция `Serialize` серийно-производного `CObject`класса обычно имеет следующую форму:

[!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_3.cpp)]

Приведенный выше шаблон кода точно такой же, `Serialize` как тот, который создает AppWizard для функции документа (класс, полученный из). `CDocument` Этот шаблон кода поможет вам написать код, который легче просмотреть, потому что код хранения и код загрузки всегда должны быть параллельными, как в следующем примере:

[!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_4.cpp)]

Библиотека определяет ** < ** и **>>** операторов для `CArchive` как первый operand и следующие типы данных и типы типа типа как вторая operand:

||||
|-|-|-|
|`CObject*`|**СИЗЕ** и`CSize`|**FLOAT**|
|**WORD**|`CString`|**POINT** и`CPoint`|
|`DWORD`|**Байт**|`RECT` и `CRect`|
|**Double**|**Длинные**|`CTime` и `CTimeSpan`|
|`Int`|**COleCurrency**|`COleVariant`|
|`COleDateTime`|`COleDateTimeSpan`||

> [!NOTE]
> Хранение и загрузка `CObject`с помощью архива требует дополнительного рассмотрения. Для получения дополнительной [Storing and Loading CObjects via an Archive](../mfc/storing-and-loading-cobjects-via-an-archive.md)информации см.

**CArchive <\< ** **>>** и операторы всегда `CArchive` возвращают ссылку на объект, который является первой операндой. Это позволяет цепочке операторов, как показано ниже:

[!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/cpp/using-the-carchive-output-and-input-operators_5.cpp)]

## <a name="see-also"></a>См. также раздел

[Сериализация. Сериализация объекта](../mfc/serialization-serializing-an-object.md)
