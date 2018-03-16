---
title: "Установка отсутствующих Microsoft времени выполнения библиотеки DLL Visual C++ | Документы Microsoft"
description: "Как найти и установить отсутствует DLL среды выполнения Visual C++."
ms.date: 03/13/2018
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6410c9753577852989172121d01c9d768f5373b3
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>Установка отсутствующих Microsoft времени выполнения библиотеки DLL Visual C++

Программы, написанные с использованием Microsoft Visual C++ часто требуются некоторые дополнительные файлы библиотеки среды выполнения Visual C++ или библиотеки DLL, для запуска. Эти среды выполнения DLL-файлы доступны в *распространяемый пакет*, библиотека файл программы-установщика для каждой версии Visual C++. Распространяемый пакет, предусмотренного в любой программе, должны быть включены в его установщиком. Если это не так, иногда можно установить распространяемый пакет самостоятельно и исправить ошибку системы при запуске программы.

Чтобы узнать, что программа отсутствует DLL среды выполнения Visual C++, если ошибка системы при запуске программы, которое говорит, что-то, как «программе не удается запустить из-за отсутствия VCRuntime140.dll с компьютера». Часто эту проблему можно устранить путем удаления программы, а затем повторите установку. Настоятельно рекомендуется повторить этот шаг во-первых, прежде чем все другие возможные исправления.

Иногда с помощью программы установки распространяемого пакета является устаревшим. Корпорацией Майкрософт обновленные версии библиотек DLL среды выполнения от времени в адрес ошибки и проблемы безопасности. Чтобы сохранить работоспособность системы безопасно и правильно, рекомендуется использовать последнее обновление для любой DLL среды выполнения. Проверьте, существует ли установка обновленного для программы, что может предоставить это обновление для вас. Если нет, затем используйте обновленный установщик для переустановки программы.

Если переустановить программу не делает Системная ошибка исчезают, затем повреждена либо поврежден установщика или библиотек среды выполнения на компьютере может быть повреждена. Попробуйте загрузить новую копию установщика для программы, и использовать его для переустановки первого. Если это не поможет, или недоступен установщик, затем может имеет смысл проверить Microsoft распространяемый пакет Visual C++ установки на компьютере.

В этой таблице показан список библиотек DLL, которые включены в один или несколько распространяемых пакетов, а также ссылки для загрузки копии распространяемого пакета. Прежде чем загружать новую копию распространяемого пакета, вы увидите, если можно исправить существующую установку.

|Отсутствует DLL  |Распространяемый пакет  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual C++ 2005 (x86) распространяемого пакета](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Распространяемый пакет Microsoft Visual C++ 2005 (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[Обновление системы безопасности MFC для распространяемого пакета Microsoft Visual C++ 2005 с пакетом обновления 1](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|ATL90.dll<br />Msvcr90.dll<br />Msvcm90.dll<br />msvcp90.dll<br />MFC90.dll<br />MFC90U.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual C++ 2008 распространяемые - x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual C++ 2008 распространяемые - x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[Обновление системы безопасности MFC для распространяемого пакета Microsoft Visual C++ 2008 с пакетом обновления 1](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|atl100.dll<br />Msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />Mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual C++ 2010 x86 распространяемого пакета](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual C++ 2010 x64 распространяемого пакета](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[Обновление системы безопасности MFC для распространяемого пакета Microsoft Visual C++ 2010 с пакетом обновления 1](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual C++ 2012 распространяемого пакета (для Visual Studio 2012 обновление 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Visual C++ 2013 распространяемый компонент Microsoft (ссылки на отдельные файлы для загрузки)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Библиотека многобайтовые MFC для Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[Среда выполнения 2013 Visual C++ для Windows 8.1 неопубликованных приложений (в формате .zip)](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />msvcp140_1.dll, etc.<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual C++ 2017 г. (x86) распространяемого пакета](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual C++ 2017 г. (x64) распространяемого пакета](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[Загрузить .NET Framework](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>Для исправления существующего распространяемого пакета

1. Откройте панель управления. В Windows 10 введите *панели управления* настольных систем поиска элемента управления в панели задач, а затем выберите **панели управления** из выбранных вариантов.

2. В панели управления выберите **программы** > **программы и компоненты**. Выберите версию распространяемого компонента Microsoft Visual C++, соответствующий библиотеки DLL, который отсутствует. Если **изменений** кнопка появляется в верхней части списка, выберите его. Если единственным вариантом является **удаления**, не может исправить этой версии распространяемого пакета.

3. Выберите **восстановления** в диалоговом окне программы установки распространяемого пакета. Может потребоваться перезагрузка после завершения восстановления.