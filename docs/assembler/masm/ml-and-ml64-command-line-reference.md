---
title: "ML and ML64 Command-Line Reference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ML"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/W* MASM compiler option"
  - "/c MASM compiler option"
  - "/EP MASM compiler option"
  - "/Fe MASM compiler option"
  - "/Zp MASM compiler option"
  - "/AT MASM compiler option"
  - "/Zm MASM compiler option"
  - "/Sf MASM compiler option"
  - "/Sp MASM compiler option"
  - "/w MASM compiler option"
  - "/Fl MASM compiler option"
  - "/coff MASM compiler option"
  - "/St MASM compiler option"
  - "/Cx MASM compiler option"
  - "/Sl MASM compiler option"
  - "/Cu MASM compiler option"
  - "MASM (Microsoft Macro Assembler), ML command-line reference"
  - "/FPi MASM compiler option"
  - "/Zf MASM compiler option"
  - "ML environment variable"
  - "/Fr MASM compiler option"
  - "/help MASM compiler option"
  - "/Sa MASM compiler option"
  - "/Zd MASM compiler option"
  - "/I MASM compiler option"
  - "/? MASM compiler option"
  - "/Bl MASM compiler option"
  - "/Fm MASM compiler option"
  - "/Fo MASM compiler option"
  - "command-line reference [ML]"
  - "/Sn MASM compiler option"
  - "/Gd MASM compiler option"
  - "/D* MASM compiler option"
  - "environment variables, ML"
  - "/Gc MASM compiler option"
  - "/F* MASM compiler option"
  - "/Sc MASM compiler option"
  - "/H MASM compiler option"
  - "/Zs MASM compiler option"
  - "/omf MASM compiler option"
  - "/Sg MASM compiler option"
  - "/Cp MASM compiler option"
  - "/Zi MASM compiler option"
  - "/nologo MASM compiler option"
  - "/Sx MASM compiler option"
  - "/WX MASM compiler option"
  - "/Ss MASM compiler option"
  - "command line, reference [ML]"
  - "/Ta MASM compiler option"
ms.assetid: 712623c6-f77e-47ea-a945-089e57c50b40
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# ML and ML64 Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Собрати и ссылки одну или несколько исходные файлы языка ассемблера.  Параметры командной строки регистр.  
  
 Дополнительные сведения о ml64.exe см. в разделе [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Синтаксис  
  
```  
ML [[options]] filename [[ [[options]]  filename]]  
ML64 [[options]] filename [[ [[options]]  filename]]  
...  
[[/link linkoptions]]  
```  
  
#### Параметры  
 `options`  
 Параметры, перечисленные в следующей таблице.  
  
|Параметр|Действие|  
|--------------|--------------|  
|**\/AT**|Включает поддержку малюсеньк\-память\-модели.  Содержит сообщения об ошибке для конструкций кода, которые нарушают требования для файлов форматирования .com.  Обратите внимание, что это не соответствует [.MODEL](../../assembler/masm/dot-model.md) **TINY** директива.<br /><br /> Не доступно в ml64.exe.|  
|**\/Bl** `filename`|Компоновщик выбирает другой.|  
|**\/c**|Только собрати.  Не связан.|  
|**\/coff**|Создает тип в формате COFF предметного модуля.  Обычно требуется для разработки языка ассемблера Win32.<br /><br /> Не доступно в ml64.exe.|  
|**\/Cp**|Сохраняет регистр всех идентификаторов пользователей.|  
|**\/Cu**|Сопоставляет все идентификаторы в верхний регистр \(по умолчанию\).<br /><br /> Не доступно в ml64.exe.|  
|**\/Cx**|Сохраняет регистр в открытых и extern символах.|  
|**\/D** `symbol`\[\[\=`value`\]\]|Определяет макрос текста с заданным именем.  If `value` отсутствует, он пуст.  Несколько токены, разделенные пробелами, должны быть заключены в кавычки.|  
|**\/EP**|Создает предварительно обработанный список источников \(отправленный в STDOUT\).  Дополнительные сведения см. в разделе **\/Sf**.|  
|**\/ERRORREPORT** \[ **NONE** &#124; **PROMPT** &#124; **QUEUE** &#124; **SEND** \]|Если ml.exe или ml64.exe завершаются ошибкой во время выполнения, можно воспользоваться **\/ERRORREPORT** отправлять в корпорацию Майкрософт сведения об этих внутренних ошибках.<br /><br /> Дополнительные сведения о **\/ERRORREPORT** см. в разделе [Параметр \/errorReport \(отчет о внутренних ошибках компилятора\)](../Topic/-errorReport%20\(Report%20Internal%20Compiler%20Errors\).md).|  
|**\/F** `hexnum`|Задает размер стека до `hexnum` байты \(это аналогично  **\/link\/STACK**.`number`\).  Значение должно быть выражено в шестнадцатеричной нотации.  Следует пробел **\/F** и  `hexnum`.|  
|**\/Fe** `filename`|Имена исполняемый файл.|  
|**\/Fl**\[\[`filename`\]\]|Создает собранный листинг кода.  Дополнительные сведения см. в разделе **\/Sf**.|  
|**\/Fm**\[\[`filename`\]\]|Создает файл сопоставления компоновщика.|  
|**\/Fo** `filename`|Имена объектный файл.  См. раздел примeчаний дополнительные сведения.|  
|**\/FPi**|Создает починка\-поднимает эмулятора числовые данные, относящиеся к арифметике с плавающей запятой \(в смешанном языка\).<br /><br /> Не доступно в ml64.exe.|  
|**\/Fr**\[\[`filename`\]\]|Создает файл обозревателя sbr источника.|  
|**\/FR**\[\[`filename`\]\]|Создает расширенную форму файла sbr источника.|  
|**\/Gc**|Указывает, что вызов и соглашений об именовании FORTRAN или функции Паскал\-стиля.  Аналогично **OPTION LANGUAGE:PASCAL**.<br /><br /> Не доступно в ml64.exe.|  
|**\/Gd**|Указывает, что вызов и соглашений об именовании функции в стиле языка C.  Аналогично **OPTION LANGUAGE:C**.<br /><br /> Не доступно в ml64.exe.|  
|**\/GZ**|Указывает, что вызов и соглашений об именовании функции \_\_stdcall.  Аналогично **OPTION LANGUAGE:STCALL**.<br /><br /> Не доступно в ml64.exe.|  
|**\/H** `number`|Ограничивает внешние имена к символам цифры значимы.  Значение по умолчанию \- 31 символов.<br /><br /> Не доступно в ml64.exe.|  
|**\/help**|Вызовы QuickHelp для справки на ML.|  
|**\/I** `pathname`|Задает путь включаемого файла.  До 10 **\/I** параметры допускаются.|  
|**\/nologo**|Подавляет сообщения для успешной сборки.|  
|**\/omf**|Создает тип формата файла предметного модуля \(OMF\) предметного модуля.  **\/omf** неявно  **\/c**; ML.exe не поддерживает связывание объектов OMF.<br /><br /> Не доступно в ml64.exe.|  
|**\/Sa**|Содержит список всех доступных сведений.|  
|**\/safeseh**|Помечает объект или не содержать никаких обработчиков исключений или содержать обработчики исключений с которыми всем объявите .SAFESEH.<br /><br /> Не доступно в ml64.exe.|  
|**\/Sf**|Добавляет перв\-пропуск, в котором для перечисления файл.|  
|**\/Sl** `width`|Устанавливает толщину линий листинга источника в символах\) в линию.  Диапазон от 60 до 255 или 0.  По умолчанию используется значение 0.  Аналогично [Страница](../../assembler/masm/page.md) ширина.|  
|**\/Sn**|Отключает таблица символов при создании списка.|  
|**\/Sp** `length`|Устанавливает длину страницы листинга источника в линиях на страницу.  Диапазон от 10 до 255 или 0.  По умолчанию используется значение 0.  Аналогично [Страница](../../assembler/masm/page.md) длина.|  
|**\/Ss** `text`|Задает текст для списка источника.  Аналогично [Подзаголовок](../../assembler/masm/subtitle.md) текст.|  
|**\/St** `text`|Определяет заголовок листинга источника.  Аналогично [НАЗВАНИЕ](../../assembler/masm/title.md) текст.|  
|**\/Sx**|Включает false условные в списке.|  
|**\/Ta** `filename`|Собирает исходный файл, имя которого не заканчивается расширением .asm.|  
|**\/w**|Аналогично **\/W0\/WX**.|  
|**\/W** `level`|Устанавливает порог предупреждений, где `level` \= 0, 1, 2 или 3.|  
|**\/WX**|Возвращает код ошибки, если предупреждения формируются.|  
|**\/X**|Пропуск ВКЛЮЧАЮЩИЙ путь среды.|  
|**\/Zd**|Создает сведения о линия\-номера в объектном файле.|  
|**\/Zf**|Делает всю открытый символов.|  
|**\/Zi**|Создает данные CodeView в объектном файле.|  
|**\/Zm**|Разрешает**M510** параметр для максимальной совместимости с MASM 5,1.<br /><br /> Не доступно в ml64.exe.|  
|**\/Zp**\[\[`alignment`\]\]|Структуры пакетов в указанной границе байта.  `alignment` может иметь значения 1, 2 или 4.|  
|**\/Zs**|Выполняет только синтаксическая проверка.|  
|**\/?**|Отображает сводку по синтаксису команд ML.|  
  
 `filename`  
 Имя файла.  
  
 `linkoptions`  
 Параметры соединения.  Дополнительные сведения см. в разделе [Параметры компоновщика](../../build/reference/linker-options.md).  
  
## Заметки  
 Некоторые параметры командной строки в ML и ML64 размещение\-чувствительны.  Например, поскольку ML и ML64 могут занимать несколько **\/c** любые соответствующие параметры  **\/Fo** параметры должны указываться раньше  **\/c**.  В следующем примере командной строки демонстрирует спецификацию файла объекта для каждой характеристики файла сборки:  
  
 **ml.exe \/Fo a1.obj \/c a.asm \/Fo b1.obj \/c b.asm**  
  
## Переменные среды  
  
|Переменная|Описание|  
|----------------|--------------|  
|INCLUDE|Указывает путь поиска включаемых файлов.|  
|ML|Указывает значение по умолчанию параметры командной строки.|  
|TMP|Задает путь для временных файлов.|  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)   
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)