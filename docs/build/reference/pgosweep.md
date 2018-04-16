---
title: pgosweep | Документы Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9680dc47d850bd49eff343c0e382b7132697858d
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="pgosweep"></a>pgosweep

Используется в профильной оптимизации для записи всех данных профиля из выполняющейся программы в файл PGC.

## <a name="syntax"></a>Синтаксис

> **pgosweep** [*параметры*] *изображения* *pgcfile*

### <a name="parameters"></a>Параметры

*Параметры* (необязательно)<br/>
Допустимые значения для *параметры* являются:

- **/?** или **/help** отображает сообщение справки.

- **/NORESET** сохраняет значение счетчика в структурах данных времени выполнения.

*image*<br/>
Полный путь файла .exe или .dll, который был создан с помощью [/genprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), или [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) параметр.

*pgcfile*<br/>
PGC-файл, где эта команда записывает данные счетчиков.

## <a name="remarks"></a>Примечания

**Pgosweep** команда работает с программами, которые были созданы с помощью [/genprofile или/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) параметр или устаревшие [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) параметр. Он прерывает выполняющуюся программу и записывает данные профиля в новый PGC-файл. По умолчанию команда обнуляет счетчики после каждой операции записи. При указании **/noreset** параметр, команда будет записывать значения, но не переустановит их в выполняющейся программе. Данный параметр предоставляет повторяющиеся данные, если впоследствии извлекать данные профиля.

Вариантом использования **pgosweep** — для получения сведений о профиле только для нормальной работы приложения. Например, можно выполнить **pgosweep** вскоре после запуска приложения и удалить этот файл. Это приведет к удалению данных профиля, связанных с издержками при запуске. Затем можно выполнить **pgosweep** до завершения работы приложения. Теперь собранные данные включают сведения о профиле только от времени, что пользователь может взаимодействовать с программой.

При именовании PGC-файл (с помощью *pgcfile* параметр) можно использовать стандартный формат *appname! n*.pgc. Если вы используете этот формат, компилятор автоматически обнаруживает эти данные в **/LTCG параметром/useprofile** или **LTCG: PGO** этап. Если вы не используете стандартного формата, необходимо использовать [pgomgr](pgomgr.md) для слияния PGC-файлы.

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

Сведения о том, как записывать данные профиля в исполняемый файл, в разделе [использованием PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Пример

В этом примере команда **pgosweep** myapp!1.pgc записывает текущие данные профиля для myapp.exe.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
