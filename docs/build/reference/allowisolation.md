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
ms.openlocfilehash: 359a68d5ec0a8c7390b5f0343530864e880a057c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493119"
---
# <a name="allowisolation"></a>/ALLOWISOLATION

Задает поведение нахождения файлов манифеста.

## <a name="syntax"></a>Синтаксис

```

/ALLOWISOLATION[:NO]
```

## <a name="remarks"></a>Примечания

**/ALLOWISOLATION** заставляет операционную систему выполнять поиск и загрузку манифеста.

По умолчанию используется **/ALLOWISOLATION** .

**/ALLOWISOLATION: нет** означает, что исполняемые файлы загружаются, как если бы манифеста не было, и заставляет `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` `DllCharacteristics` [ссылку EDITBIN](editbin-reference.md) задать бит в поле необязательного заголовка.

Если изоляция для исполняемого файла отключена, загрузчик Windows не пытается найти манифест приложения для нового процесса. Новый процесс не имеет контекста активации по умолчанию, даже если существует манифест в самом исполняемом файле или если имеется манифест с именем *Executable*. exe. manifest.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)<br/>
[/ALLOWISOLATION (поиск манифеста)](allowisolation-manifest-lookup.md)<br/>
[Справочник по файлам манифеста](/windows/win32/SbsCs/manifest-files-reference)
