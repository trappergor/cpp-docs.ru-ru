---
title: 'Руководство по переносу: MFC Scribble'
ms.date: 10/23/2019
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
ms.openlocfilehash: 789d29effeea76045a4a10fbca19f20d06778f7c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076967"
---
# <a name="porting-guide-mfc-scribble"></a>Руководство по переносу: MFC Scribble

Этот раздел — первый из нескольких подразделов, в которых рассматриваются процедуры обновления проектов Visual Studio C++, созданных в более ранних версиях Visual Studio до Visual Studio 2017. В этих подразделах на примерах описывается процесс обновления начиная с очень простого проекта с постепенным повышением уровня сложности. В этом подразделе будет рассмотрен процесс обновления для конкретного проекта MFC Scribble. Он подходит в качестве базового примера для процесса обновления для проектов C++.

Каждая версия Visual Studio может иметь некоторые несовместимости, что может усложнять перемещение кода из более старой версии Visual Studio в новую. Иногда необходимые изменения есть в вашем коде, поэтому код необходимо перекомпилировать и обновлять. В других случаях необходимые изменения относятся к файлам проекта. При открытии проекта, созданного в предыдущей версии Visual Studio, система автоматически предлагает обновить версию проекта или решения. Эти средства обычно обновляют только файлы проекта (они не изменяют исходный код).

## <a name="mfc-scribble"></a>MFC Scribble

MFC Scribble — это широко известный пример, который был включен в разные версии Visual C++. Это простое приложение для рисования, демонстрирующее некоторые основные возможности MFC. Существуют различные версии данного приложения — как управляемые версии, так и версии в машинном коде. Для этого примера взята старая версия Scribble в машинном коде из Visual Studio 2005 и открыта в Visual Studio 2017.

Перед обновлением убедитесь, что установлена рабочая нагрузка "Рабочий стол Windows". Откройте установщик Visual Studio (vs_installer.exe). Воспользуйтесь таким способом: выберите **Файл** > **Создать проект** и перейдите к нижней части списка установленных шаблонов, где вы увидите **Открыть Visual Studio Installer**. После открытия установщика вы увидите все доступные рабочие нагрузки. Если рабочая нагрузка **Рабочий стол Windows** не выбрана, выберите ее и нажмите кнопку **Изменить** в нижней части окна.

Затем создайте резервную копию всего решения и всего его содержимого.

Наконец, откройте решение в последней версии Visual Studio и позвольте мастеру преобразовать проект.

Обратите внимание, что devenv можно также запускать из командной строки с помощью параметра `/Upgrade`, а не использовать мастер для обновления проектов. См. статью [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe). Это может оказаться полезным для автоматизации процесса обновления для большого количества проектов.

### <a name="step-1-converting-the-project-file"></a>Шаг 1. Преобразование файла проекта

При открытии старого файла проекта в Visual Studio Visual Studio предлагает преобразовать файл проекта в последнюю версию, которую мы приняли. Появляется следующее диалоговое окно:

![Проверка изменений проекта и решения](../porting/media/scribbleprojectupgrade.PNG "Просмотр проекта и изменения в решении")

Произошла ошибка, указывающая, что целевой объект Itanium недоступен и не будет преобразован.

```Output
Platform 'Itanium' is missing from this project. All the configurations and their file configuration settings specific to this platform will be ignored. If you want this platform converted, please make sure you have the corresponding platform installed under '%vctargetpath%\platforms\Itanium'.Continue to convert this project without this platform?
```

На момент создания предыдущего проекта Scribble платформа Itanium представляла собой важную целевую платформу. Платформа Windows больше не поддерживает Itanium, поэтому следует выбрать вариант продолжения без поддержки платформы Itanium.

Затем Visual Studio отображает отчет о миграции, в котором указываются все проблемы со старым файлом проекта.

![Обновить отчет](../porting/media/scribblemigrationreport.PNG "Отчет об обновлении")

В этом случае проблемами были все предупреждения, а программа Visual Studio внесла соответствующие изменения в файл проекта. Применительно к проекту существенная разница заключается в том, что изменился инструмент сборки: вместо vcbuild применяется msbuild. Это изменение впервые появилось в Visual Studio 2010. К другим изменениям относится другая последовательность элементов в самом файле проекта. Никакие другие проблемы применительно к этому простому проекту рассматривать не нужно.

### <a name="step-2-getting-it-to-build"></a>Шаг 2. Выполнение сборки до достижения успеха

Перед сборкой необходимо проверить набор инструментов платформы, чтобы узнать, какую версию компилятора использует система проекта. В диалоговом окне "Свойства проекта" в разделе **Свойства конфигурации** в категории **Общая** взгляните на свойство **Набор инструментов платформы**. Оно содержит версию Visual Studio и номер версии набора инструментов платформы, в данном случае — v141 для версии Visual Studio 2017 инструментов. При преобразовании проекта, который был изначально скомпилирован с Visual Studio 2010, 2012, 2013 или 2015, набор инструментов не обновляется автоматически до последнего набора инструментов.

Чтобы переключиться на Юникод, откройте свойства проекта в разделе **Свойства конфигурации**, выберите раздел **Общее** и найдите свойство **Кодировка**. Измените значение с **Использовать многобайтовую кодировку** на **Использовать кодировку Юникод**. В результате данного изменения определены макросы _UNICODE и UNICODE, а _MBCS не определен. Это можно проверить в диалоговом окне "Свойства" в категории **C/C++** в свойстве **Командная строка**.

```Output
/GS /analyze- /W4 /Zc:wchar_t /Zi /Gm- /Od /Fd".\Debug\vc141.pdb" /Zc:inline /fp:precise /D "_AFXDLL" /D "WIN32" /D "_DEBUG" /D "_WINDOWS" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX /Zc:forScope /Gd /Oy- /MDd /Fa".\Debug\" /EHsc /nologo /Fo".\Debug\" /Fp".\Debug\Scribble.pch" /diagnostics:classic
```

Несмотря на то что проект Scribble не был настроен для компиляции с символами Юникода, он был уже записан с TCHAR вместо char, поэтому фактически ничего не нужно изменять. Сборка проекта выполняется успешно с кодировкой Юникод.

Теперь выполним сборку решения. В окне вывода компилятор сообщает, что _WINNT32_WINNT не определен:

```Output
_WIN32_WINNT not defined. Defaulting to _WIN32_WINNT_MAXVER (see WinSDKVer.h)
```

Это предупреждение, а не сообщение об ошибке, которое появляется очень часто при обновлении проекта Visual Studio C++. Это макрос, который определяет, в какой самой ранней версии Windows будет запускаться приложение. Если проигнорировать предупреждение, принимается значение по умолчанию (_WIN32_WINNT_MAXVER), то есть будет использоваться текущая версия Windows. Таблицу возможных значений см. в статье [Using the Windows Headers](/windows/win32/WinProg/using-the-windows-headers) (Использование заголовков Windows). Например, можно выбрать вариант запуска в любой версии, начиная с Vista.

```cpp
#define _WIN32_WINNT _WIN32_WINNT_VISTA
```

Если код использует части интерфейса Windows API, недоступные в версии Windows, которая указана с помощью этого макроса, должно появиться сообщение об ошибке компилятора. В случае кода Scribble ошибки отсутствуют.

### <a name="step-3-testing-and-debugging"></a>Шаг 3. Тестирование и отладка

Набор тестов отсутствует. Мы только что запустили приложение, вручную протестировали его функции с помощью пользовательского интерфейса. Проблемы не обнаружены.

### <a name="step-4-improve-the-code"></a>Шаг 4. Улучшение кода

Теперь, после перехода на Visual Studio 2017, может потребоваться внести некоторые изменения, чтобы воспользоваться преимуществами новых возможностей C++. Текущая версия компилятора C++ намного лучше соответствует стандарту C++, чем предыдущие версии, поэтому, при желании внести в код некоторые изменения, чтобы сделать его более безопасным и более переносимым в другие компиляторы и операционные системы, следует учитывать ряд усовершенствований.

## <a name="next-steps"></a>Следующие шаги

Scribble представляла собой небольшое и простое классическое приложение Windows, которое было несложно преобразовывать. Многие небольшие, простые приложения также можно легко преобразовывать в новую версию.  Для более сложных приложений, содержащих много строк кода, старого традиционного кода, который может не соответствовать современным инженерным стандартам, различных проектов и библиотек, настраиваемых этапов построения или для сложных скриптовых автоматизированных построений, процедура обновления займет больше времени. Перейдем к [следующему примеру](../porting/porting-guide-com-spy.md), к приложению ATL/COM, которое называется COM Spy.

## <a name="see-also"></a>См. также:

[Перенос и обновление: примеры и конкретные случаи](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Next Example: COM Spy](../porting/porting-guide-com-spy.md) (Следующий пример: COM Spy)
