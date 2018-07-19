---
title: Справочник по командной строке ML и ML64 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ML
dev_langs:
- C++
helpviewer_keywords:
- /W* MASM compiler option
- /c MASM compiler option
- /EP MASM compiler option
- /Fe MASM compiler option
- /Zp MASM compiler option
- /AT MASM compiler option
- /Zm MASM compiler option
- /Sf MASM compiler option
- /Sp MASM compiler option
- /w MASM compiler option
- /Fl MASM compiler option
- /coff MASM compiler option
- /St MASM compiler option
- /Cx MASM compiler option
- /Sl MASM compiler option
- /Cu MASM compiler option
- MASM (Microsoft Macro Assembler), ML command-line reference
- /FPi MASM compiler option
- /Zf MASM compiler option
- ML environment variable
- /Fr MASM compiler option
- /help MASM compiler option
- /Sa MASM compiler option
- /Zd MASM compiler option
- /I MASM compiler option
- /? MASM compiler option
- /Bl MASM compiler option
- /Fm MASM compiler option
- /Fo MASM compiler option
- command-line reference [ML]
- /Sn MASM compiler option
- /Gd MASM compiler option
- /D* MASM compiler option
- environment variables, ML
- /Gc MASM compiler option
- /F* MASM compiler option
- /Sc MASM compiler option
- /H MASM compiler option
- /Zs MASM compiler option
- /omf MASM compiler option
- /Sg MASM compiler option
- /Cp MASM compiler option
- /Zi MASM compiler option
- /nologo MASM compiler option
- /Sx MASM compiler option
- /WX MASM compiler option
- /Ss MASM compiler option
- command line, reference [ML]
- /Ta MASM compiler option
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da3fb143aeaaf6fa8cf31c45b31707fa01bf6898
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057803"
---
# <a name="ml-and-ml64-command-line-reference"></a>Справочник по командной строке ML и ML64
Выполняет сборку и связывает один или несколько исходных файлов языка ассемблера. Параметры командной строки учитывается регистр символов.  
  
 Дополнительные сведения о ml64.exe см. в разделе [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### <a name="parameters"></a>Параметры  
 `options`  
 Параметры, перечисленные в следующей таблице.  
  
|Параметр|Действие|  
|------------|------------|  
|**/AT**|Включает поддержку очень мала модели памяти. Включает сообщения об ошибках для конструкций кода соответствуют требованиям для .com файлы форматирования. Обратите внимание, что это не эквивалентно [. МОДЕЛЬ](../../assembler/masm/dot-model.md) **очень МЕЛКИЕ** директивы.<br /><br /> Недоступно в ml64.exe.|  
|**/Bl** `filename`|Выбор альтернативного компоновщика.|  
|**/c**|Собирает только. Не содержит ссылок.|  
|**/coff**|Создает общий объект файла формате COFF тип объекта модуля. Как правило, требуется для разработки приложений Win32 языка ассемблера.<br /><br /> Недоступно в ml64.exe.|  
|**/Cp**|Сохраняет все идентификаторы пользователей.|  
|**/Cu**|Сопоставляет все идентификаторы в верхний регистр (по умолчанию).<br /><br /> Недоступно в ml64.exe.|  
|**/Cx**|Сохраняет регистр в символы public и extern.|  
|**/D** `symbol`[[=`value`]]|Определяет макрос текст с заданным именем. Если `value` является отсутствует, это свойство пусто. Несколько токенов, разделенных пробелами должны заключаться в кавычки.|  
|**/EP**|Создает список предварительно обработанных исходных (направляются в STDOUT). В разделе **/Sf**.|  
|**/ ERRORREPORT** [ **NONE** &AMP;#124; **PROMPT** &AMP;#124; **ОЧЕРЕДИ** &AMP;#124; **ОТПРАВКИ** ]|Если ml.exe ml64.exe сбоя или во время выполнения можно использовать **/errorReport** в корпорацию Майкрософт сведения об этих ошибках.<br /><br /> Дополнительные сведения о **/errorReport**, в разделе [/errorReport (отчет внутренних ошибках компилятора)](../../build/reference/errorreport-report-internal-compiler-errors.md).|  
|**/F** `hexnum`|Задает размер для стека `hexnum` байт (это то же самое, как **/связь/СТЕК**:`number`). Значения должны быть выражены в шестнадцатеричном формате. Должен быть пробел между **/F** и `hexnum`.|  
|**/FE** `filename`|Имя исполняемого файла.|  
|**/Fl**[[`filename`]]|Создает список собранного кода. В разделе **/Sf**.|  
|**Параметр /FM**[[`filename`]]|Создает файл сопоставления компоновщика.|  
|**/FO** `filename`|Имя объектного файла. См. раздел Примечания для получения дополнительной информации.|  
|**/FPi**|Создает эмулятор исправлений арифметики с плавающей запятой (смешанного типа имеется только).<br /><br /> Недоступно в ml64.exe.|  
|**/Fr**[[`filename`]]|Создает SBR-файл обозревателя исходного.|  
|**/FR**[[`filename`]]|Создает SBR-файл обозревателя исходного расширенной формы.|  
|**/Gc**|Указывает, используется функция FORTRAN или Pascal стиль вызова и соглашения об именовании. То же, что **параметр языка: PASCAL**.<br /><br /> Недоступно в ml64.exe.|  
|**/Gd**|Указывает, используется функция C-стиле, вызов и соглашения об именовании. То же, что **параметр языка: C**.<br /><br /> Недоступно в ml64.exe.|  
|**/GZ**|Указывает, используется функция __stdcall вызова и соглашения об именовании.  То же, что **параметр языка: STCALL**.<br /><br /> Недоступно в ml64.exe.|  
|**/H** `number`|Ограничивает число значимых символов внешних имен. Значение по умолчанию — 31 символов.<br /><br /> Недоступно в ml64.exe.|  
|**/help**|Вызывает QuickHelp для получения справки по машинного Обучения.|  
|**/I** `pathname`|Задает путь для включаемого файла. Не более 10 **/i** использовать параметры.|  
|**/nologo**|Подавляет сообщения для успешной сборки.|  
|**/ OMF**|Создает тип объекта модуля файла форматирования (OMF) объекта модуля.  **/ OMF** подразумевает **/c**; ML.exe не поддерживает связывание объектов OMF.<br /><br /> Недоступно в ml64.exe.|  
|**/Sa**|Включает список всех доступных сведений.|  
|**/safeseh**|Помечает объект как содержащий нет обработчиков исключений или содержащая обработчики исключений, которые объявлены с [. SAFESEH](../../assembler/masm/dot-safeseh.md).<br /><br /> Недоступно в ml64.exe.|  
|**/Sf**|Добавляет файл листинга для листинга начальным.|  
|**/Sl** `width`|Задает толщину линии в символов в строке источника. Диапазон — 60 до 255 или 0. По умолчанию — 0. То же, что [страницы](../../assembler/masm/page.md) ширины.|  
|**/Sn**|При создании списка отключает таблицы символов.|  
|**/Sp** `length`|Задает длину страницы в строк на странице источника. Диапазон — 10 до 255 или 0. По умолчанию — 0. То же, что [страницы](../../assembler/masm/page.md) длины.|  
|**/Ss** `text`|Задает текст для исходного списка. То же, что [ПОДЗАГОЛОВОК](../../assembler/masm/subtitle.md) текста.|  
|**/ST** `text`|Указывает название для исходного списка. То же, что [заголовок](../../assembler/masm/title.md) текста.|  
|**/Sx**|Включает значение false, условные выражения в списке.|  
|**/TA** `filename`|Выполняет сборку, имя которого заканчивается расширением .asm исходного файла.|  
|**/w**|То же, что **/W0/WX**.|  
|**/W** `level`|Задает уровень предупреждений, где `level` = 0, 1, 2 или 3.|  
|**/WX**|Возвращает код ошибки, если создаются предупреждения.|  
|**/X**|Игнорируйте путь к среды INCLUDE.|  
|**/Zd**|Создает информацию о номерах строк в объектном файле.|  
|**/Zf**|Делает все символы открытый.|  
|**/Zi**|Создает Информация CodeView в объектном файле.|  
|**/Zm**|Включает**M510** параметр для максимальной совместимости с MASM 5.1.<br /><br /> Недоступно в ml64.exe.|  
|**/Zp**[[`alignment`]]|Упаковывает структуры в указанный байтовой границе. `alignment` Может быть 1, 2 или 4.|  
|**/Zs**|Выполняет только синтаксическая проверка.|  
|**/?**|Отображает сводку о синтаксисе командной строки машинного Обучения.|  
  
 `filename`  
 Имя файла  
  
 `linkoptions`  
 Параметры ссылок.  В разделе [параметры компоновщика](../../build/reference/linker-options.md) для получения дополнительной информации.  
  
## <a name="remarks"></a>Примечания  
 Некоторые параметры командной строки для ML и ML64 чувствительны к размещения. Например так как ML и ML64 может принимать несколько **/c** параметры все соответствующие **/Fo** параметры должны указываться перед **/c**. Следующий пример командной строки показано спецификацию файла объекта для каждого спецификация файла сборки.  
  
 **/Fo ML.exe a1.obj /c a.asm /Fo b1.obj /c b.asm**  
  
## <a name="environment-variables"></a>Переменные среды  
  
|Переменная|Описание|  
|--------------|-----------------|  
|INCLUDE|Путь поиска включаемых файлов.|  
|ML|Задает параметры командной строки по умолчанию.|  
|TMP|Указывает путь для временных файлов.|  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)   
 [Справочные материалы по ассемблеру Microsoft Macro Assembler](../../assembler/masm/microsoft-macro-assembler-reference.md)