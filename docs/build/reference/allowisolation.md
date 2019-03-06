---
title: /ALLOWISOLATION
ms.date: 11/04/2016
f1_keywords:
- /ALLOWISOLATION
helpviewer_keywords:
- -ALLOWISOLATION editbin option
- /ALLOWISOLATION editbin option
- ALLOWISOLATION editbin option
ms.assetid: 91430344-f64f-491a-a5a5-7ea3b21cbe68
ms.openlocfilehash: ac9d1f067259b092a261702b51f2355d4f908469
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417444"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Задает поведение нахождения файлов манифеста.

## <a name="syntax"></a>Синтаксис

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Примечания

**/ ALLOWISOLATION** вынуждает операционную систему на поиск и загрузку манифеста.

**/ ALLOWISOLATION** используется по умолчанию.

**/ALLOWISOLATION:no** указывает, что исполняемые файлы загружены, как если бы без манифеста, а также причины [Справочник ЕDITBIN](../../build/reference/editbin-reference.md) присвоить `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` бит в необязательном заголовке `DllCharacteristics` поля.

Если изоляция для исполняемого файла отключена, загрузчик Windows не пытается найти манифест приложения для нового процесса. Новый процесс не имеет контекста активации по умолчанию, даже в том случае, если отсутствует манифест в исполняемом файле сам или при наличии манифеста с именем *имя исполняемого файла*. exe.manifest.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)<br/>
[/ALLOWISOLATION (поиск манифеста)](../../build/reference/allowisolation-manifest-lookup.md)<br/>
[Ссылки на файлы манифеста](/windows/desktop/SbsCs/manifest-files-reference)
