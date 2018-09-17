---
title: pgosweep | Документация Майкрософт
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
ms.workload:
- cplusplus
ms.openlocfilehash: ed12828d9170aac576a97c63b9988bb4b303ef58
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711923"
---
# <a name="pgosweep"></a>pgosweep

Используется в профильной оптимизации для записи всех данных профиля из выполняющейся программы к PGC-файл.

## <a name="syntax"></a>Синтаксис

> **pgosweep** [*параметры*] *изображение* *pgcfile*

### <a name="parameters"></a>Параметры

*options*<br/>
(Необязательно) Допустимые значения для *параметры* являются:

- **/?** или **/help** отображает сообщение справки.

- **вычистки** ведет счет в структур данных времени выполнения.

*Изображение*<br/>
Полный путь файла .exe или .dll, который был создан с помощью [/genprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md), или [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) параметр.

*pgcfile*<br/>
PGC-файл, где эта команда записывает данные счетчиков.

## <a name="remarks"></a>Примечания

**Pgosweep** команда работает для программ, которые были созданы с помощью [/genprofile или/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) параметр или устаревший [/LTCG: PGINSTRUMENT](ltcg-link-time-code-generation.md) параметр. Он прерывает выполнение программы и записывает данные профиля для нового PGC-файл. По умолчанию команда сбрасывает счетчики после каждой операции записи. Если указать **вычистки** параметр, команда будет записывать значения, но не сбросить их в выполняющейся программе. Этот параметр обеспечивает повторяющихся данных, если впоследствии извлекать данные профиля.

Вариантом использования **pgosweep** — для получения сведений о профиле для нормальной работы приложения. Например, можно выполнить **pgosweep** вскоре после запуска приложения и отменить этот файл. Это приведет к удалению данных профиля, связанный с издержками при запуске. Затем можно выполнить **pgosweep** до завершения работы приложения. Теперь собранные данные включают данные профиля, только от времени пользователь может взаимодействовать с программой.

Имени PGC-файл (с помощью *pgcfile* параметр) можно использовать стандартный формат, который является *appname! n*.pgc. Если вы используете этот формат, компилятор автоматически обнаруживает эти данные в **/LTCG/useprofile** или **LTCG: PGO** этапа. Если вы не используете стандартный формат, необходимо использовать [pgomgr](pgomgr.md) для слияния PGC-файлы.

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

Сведения о том, как собирать данные из профиля в исполняемый файл, см. в разделе [использованием PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Пример

В этом примере команда **pgosweep** записывает текущие данные профиля для myapp.exe myapp!1.pgc.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
