---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341187"
---
# <a name="pgosweep"></a>pgosweep

Используется при профильной оптимизации для записи всех данных профиля из выполняемой программы в PGC-файл.

## <a name="syntax"></a>Синтаксис

> **pgosweep** [*options*] *image* *pgcfile*

### <a name="parameters"></a>Параметры

*options*<br/>
(Необязательно) Допустимые значения для *options*:

- **/?** или **/help** — выводит справочное сообщение.

- **/noreset** сохраняет счетчик в структурах данных времени выполнения.

*изображение*<br/>
Полный путь к EXE- или DLL-файлу, созданному с использованием параметра [/GENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) или [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md).

*pgcfile*<br/>
Файл PGC, в который эта команда записывает счетчики данных.

## <a name="remarks"></a>Примечания

Команда **pgosweep** работает с программами, собранными с использованием параметра [/GENPROFILE или /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) либо нерекомендуемого параметра [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md). Она прерывает выполнение программы и записывает данные профиля в новый PGC-файл. По умолчанию команда сбрасывает счетчики после каждой операции записи. Если указать параметр **/noreset**, команда будет записывать значения, но не будет сбрасывать их в выполняющейся программе. Этот параметр приводит к дублированию данных при последующем извлечении данных профиля.

Альтернативный вариант использования **pgosweep** — получение данных профиля только для нормального режима работы приложения. Например, можно запустить **pgosweep** вскоре после запуска приложения и удалить этот файл. Это приведет к удалению данных профиля, связанных с запуском. После этого можно запустить **pgosweep** перед завершением работы приложения. В результате будут собраны данные профиля только с момента, когда пользователь получил возможность взаимодействовать с программой.

При присвоении имени PGC-файлу (с помощью параметра *pgcfile*) можно использовать стандартный формат, то есть *appname!n*.pgc. При использовании такого формата компилятор автоматически находит данные на этапе **/LTCG /USEPROFILE** или **/LTCG:PGO**. Если стандартный формат не применяется, необходимо использовать параметр [pgomgr](pgomgr.md) для слияния файлов PGC.

> [!NOTE]
> Это средство можно запустить только из командной строки разработчика Visual Studio. В системной командной строке или проводнике это невозможно.

Сведения о записи данных профиля из исполняемого файла см. в разделе [PgoAutoSweep](pgoautosweep.md).

## <a name="example"></a>Пример

В этом примере программа **pgosweep** записывает текущие данные профиля для myapp.exe в файл myapp!1.pgc.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
