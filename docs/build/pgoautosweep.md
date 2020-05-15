---
title: PgoAutoSweep
ms.date: 07/02/2019
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
ms.openlocfilehash: 57bcd1b2e9f0a3312867c4373fd1e50bcf91576e
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552247"
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` сохраняет текущие сведения счетчиков профиля в файл, а затем сбрасывает эти счетчики. Эта функция применяется при обучении профильной оптимизации для записи всех данных профиля из выполняющейся программы в файл `.pgc`, который в дальнейшем будет использоваться в оптимизационной сборке.

## <a name="syntax"></a>Синтаксис

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Параметры

*name*<br/>
Строка идентификации для сохраненного файла `.pgc`.

## <a name="remarks"></a>Примечания

Функцию `PgoAutoSweep` можно вызывать из приложения, чтобы сохранить и сбросить данные профиля в любой момент во время выполнения приложения. В инструментированной сборке `PgoAutoSweep` записывает текущие данные профилирования, сохраняет их в файле и сбрасывает счетчики профиля. Это работает аналогично вызову команды [pgosweep](pgosweep.md) в конкретной точке исполняемого файла. В оптимизированной сборке `PgoAutoSweep` не работает.

Сохраненные данные счетчиков профиля помещаются в файл с именем *базовое_имя*-*имя*!*значение*.pgc, где *базовое_имя* — это базовое имя исполняемого файла, *имя* — параметр, переданный в `PgoAutoSweep`, и *значение* — уникальное значение, обычно монотонно увеличивающееся число, для предотвращения конфликтов имен файлов.

Чтобы использовать файл `.pgc`, созданный функцией `PgoAutoSweep` для создания оптимизированного исполняемого файла, его необходимо объединить с файлом `.pgd`. Такое слияние можно выполнить с помощью команды [pgomgr](pgomgr.md).

Имя объединенного файла `.pgd` можно передать компоновщику во время оптимизационной сборки с помощью аргумента **PGD=** _имя_файла_ в параметре компоновщика [/USEPROFILE](reference/useprofile.md) или с помощью нерекомендуемого параметра компоновщика **/PGD**. При объединении файлов `.pgc` в файл с именем *базовое_имя*.pgd не нужно указывать имя файла в командной строке, так как компоновщик выбирает его по умолчанию.

Функция `PgoAutoSweep` поддерживает параметр потокобезопасности, заданный при создании инструментированной сборки. Если вы используете параметр по умолчанию или задаете аргумент **NOEXACT** в параметре компоновщика [/GENPROFILE или /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), вызовы функции `PgoAutoSweep` не являются потокобезопасными. При использовании аргумента **EXACT** создается потокобезопасный и более точный, но и более медленный инструментированный исполняемый файл.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h>|

Исполняемый файл должен включать файл pgobootrun.lib в скомпонованных библиотеках. Этот файл входит в установку Visual Studio и находится в каталоге библиотек VC для каждой поддерживаемой архитектуры.

## <a name="example"></a>Пример

В приведенном ниже примере функция `PgoAutoSweep` используется для создания двух файлов `.pgc` в разных точках во время выполнения. Первый файл содержит данные, описывающие поведение среды выполнения, пока значение `count` не достигло 3, а второй файл содержит данные, собранные после этой точки и до завершения приложения.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

В командной строке разработчика скомпилируйте код в объектный файл с помощью следующей команды:

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Затем создайте инструментированную сборку для обучения с помощью следующей команды:

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Запустите инструментированный исполняемый файл для записи данных для обучения. Выходные данные, полученные в результате вызовов функции `PgoAutoSweep`, сохраняются в файлах с именами pgoautosweep-func1!1.pgc и pgoautosweep-func2!1.pgc. Выходные данные программы должны выглядеть следующим образом:

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

Объедините сохраненные данные в базу данных обучения профиля, выполнив команду **pgomgr**:

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

Результат выполнения этой команды выглядит следующим образом:

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Теперь вы можете использовать эти данные для обучения, чтобы создать оптимизированную сборку. Чтобы создать оптимизированный исполняемый файл, введите следующую команду:

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>См. также

[Профильная оптимизация](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
