---
title: "Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
caps.latest.revision: 15
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 15
---
# Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows
Многие функции среды выполнения C \(CRT\) недоступны при построении приложений универсальной платформы Windows. В некоторых случаях доступны обходные решения: например, можно использовать API\-интерфейсы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] или Win32. Однако в других случаях функции CRT запрещены, поскольку соответствующие им функции или вспомогательные API не могут применяться к приложениям UWP.  
  
 В следующей таблице перечислены функции CRT, которые недоступны при построении приложений UWP, и приведены применимые решения.  
  
## Неподдерживаемые функции CRT  
  
||||  
|-|-|-|  
|\_beep \_sleep \_seterrormode|Эти функции устарели в предыдущих версиях CRT. Кроме того, соответствующие API Win32 недоступны для приложений UWP.|Обходное решение отсутствует.|  
|chdir \_chdrive getcwd|Эти функции являются устаревшими или не являются потокобезопасными.|Используйте \_chdir, \_getcwd и связанные функции.|  
|\_cgets \_cgets\_s \_cgetws \_cgetws\_s \_cprintf \_cprintf\_l \_cprintf\_p \_cprintf\_p\_l \_cprintf\_s \_cprintf\_s\_l \_cputs \_cputws \_cscanf \_cscanf\_l \_cscanf\_s \_cscanf\_s\_l \_cwait \_cwprintf \_cwprintf\_l \_cwprintf\_p \_cwprintf\_p\_l \_cwprintf\_s \_cwprintf\_s\_l \_cwscanf \_cwscanf\_l \_cwscanf\_s \_cwscanf\_s\_l \_vcprintf \_vcprintf\_l \_vcprintf\_p \_vcprintf\_p\_l \_vcprintf\_s \_vcprintf\_s\_l \_vcwprintf \_vcwprintf\_l \_vcwprintf\_p \_vcwprintf\_p\_l \_vcwprintf\_s \_vcwprintf\_s\_l \_getch \_getch\_nolock \_getche \_getche\_nolock \_getwch \_getwch\_nolock \_getwche \_getwche\_nolock \_putch \_putch\_nolock \_putwch \_putwch\_nolock \_ungetch \_ungetch\_nolock \_ungetwch \_ungetwch\_nolock \_kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|Эти функции используются для чтения напрямую с консоли и записи на консоль. Приложения UWP имеют только графический пользовательский интерфейс и не поддерживают консоль.|Обходное решение отсутствует.|  
|getpid|Эта функция устарела.|Используйте \_getpid или API Win32 `GetCurrentProcessId()`.|  
|\_getdiskfree|Недоступно.|Используйте API Win32 `GetDiskFreeSpaceExW()`.|  
|\_getdrive \_getdrives|Соответствующий API недоступен для приложений UWP.|Обходное решение отсутствует.|  
|\_inp \_inpd \_inpw \_outp \_outpd \_outpw inp inpd inpw outp outpd outpw|Ввод\-вывод через порты не поддерживается в приложениях UWP.|Обходное решение отсутствует.|  
|\_ismbcalnum \_ismbcalnum\_l \_ismbcalpha \_ismbcalpha\_l \_ismbcdigit \_ismbcdigit\_l \_ismbcgraph \_ismbcgraph\_l \_ismbchira \_ismbchira\_l \_ismbckata \_ismbckata\_l \_ismbcl0 \_ismbcl0\_l \_ismbcl1 \_ismbcl1\_l \_ismbcl2 \_ismbcl2\_l \_ismbclegal \_ismbclegal\_l \_ismbclower \_ismbclower\_l \_ismbcprint \_ismbcprint\_l \_ismbcpunct \_ismbcpunct\_l \_ismbcspace \_ismbcspace\_l \_ismbcsymbol \_ismbcsymbol\_l \_ismbcupper \_ismbcupper\_l \_mbbtombc \_mbbtombc\_l \_mbbtype \_mbbtype\_l \_mbccpy \_mbccpy\_l \_mbccpy\_s \_mbccpy\_s\_l \_mbcjistojms \_mbcjistojms\_l \_mbcjmstojis \_mbcjmstojis\_l \_mbclen \_mbclen\_l \_mbctohira \_mbctohira\_l \_mbctokata \_mbctokata\_l \_mbctolower \_mbctolower\_l \_mbctombb \_mbctombb\_l \_mbctoupper \_mbctoupper\_l \_mbsbtype \_mbsbtype\_l \_mbscat \_mbscat\_l \_mbscat\_s \_mbscat\_s\_l \_mbschr \_mbschr\_l \_mbscmp \_mbscmp\_l \_mbscoll \_mbscoll\_l \_mbscpy \_mbscpy\_l \_mbscpy\_s \_mbscpy\_s\_l \_mbscspn \_mbscspn\_l \_mbsdec \_mbsdec\_l \_mbsicmp \_mbsicmp\_l \_mbsicoll \_mbsicoll\_l \_mbsinc \_mbsinc\_l \_mbslen \_mbslen\_l \_mbslwr \_mbslwr\_l \_mbslwr\_s \_mbslwr\_s\_l \_mbsnbcat \_mbsnbcat\_l \_mbsnbcat\_s \_mbsnbcat\_s\_l \_mbsnbcmp \_mbsnbcmp\_l \_mbsnbcnt \_mbsnbcnt\_l \_mbsnbcoll \_mbsnbcoll\_l \_mbsnbcpy \_mbsnbcpy\_l \_mbsnbcpy\_s \_mbsnbcpy\_s\_l \_mbsnbicmp \_mbsnbicmp\_l \_mbsnbicoll \_mbsnbicoll\_l \_mbsnbset \_mbsnbset\_l \_mbsnbset\_s \_mbsnbset\_s\_l \_mbsncat \_mbsncat\_l \_mbsncat\_s \_mbsncat\_s\_l \_mbsnccnt \_mbsnccnt\_l \_mbsncmp \_mbsncmp\_l \_mbsncoll \_mbsncoll\_l \_mbsncpy \_mbsncpy\_l \_mbsncpy\_s \_mbsncpy\_s\_l \_mbsnextc \_mbsnextc\_l \_mbsnicmp \_mbsnicmp\_l \_mbsnicoll \_mbsnicoll\_l \_mbsninc \_mbsninc\_l \_mbsnlen \_mbsnlen\_l \_mbsnset \_mbsnset\_l \_mbsnset\_s \_mbsnset\_s\_l \_mbspbrk \_mbspbrk\_l \_mbsrchr \_mbsrchr\_l \_mbsrev \_mbsrev\_l \_mbsset \_mbsset\_l \_mbsset\_s \_mbsset\_s\_l \_mbsspn \_mbsspn\_l \_mbsspnp \_mbsspnp\_l \_mbsstr \_mbsstr\_l \_mbstok \_mbstok\_l \_mbstok\_s \_mbstok\_s\_l \_mbsupr \_mbsupr\_l \_mbsupr\_s \_mbsupr\_s\_l is\_wctype|Многобайтовые строки не поддерживаются в приложениях UWP.|Используйте вместо них строки Юникода.|  
|\_pclose \_pipe \_popen \_wpopen|Именованные каналы недоступны для приложений UWP.|Обходное решение отсутствует.|  
|\_resetstkoflw|Вспомогательные API Win32 недоступны для приложений UWP.|Обходное решение отсутствует.|  
|\_getsystime \_setsystime|Эти API устарели в предыдущих версиях CRT. Кроме того, пользователь не может задать системное время в приложении UWP из\-за отсутствия необходимых разрешений.|Для получения системного времени используйте API Win32 `GetSystemTime`. Системное время нельзя устанавливать.|  
|\_environ \_putenv \_putenv\_s \_searchenv \_searchenv\_s \_dupenv\_s \_wputenv \_wputenv\_s \_wsearchenv getenv getenv\_s putenv \_wdupenv\_s \_wenviron \_wgetenv \_wgetenv\_s \_wsearchenv\_s tzset|Переменные среды недоступны для приложений UWP.|Обходное решение отсутствует. Чтобы установить часовой пояс, используйте \_tzset.|  
|\_loaddll \_getdllprocaddr \_unloaddll|Эти функции устарели в предыдущих версиях CRT. Кроме того, пользователь не может загружать библиотеки DLL, отличные от DLL из пакета самого приложения.|Для загрузки и использования упакованных DLL следует применять API Win32 `LoadPackagedLibrary`, `GetProcAddress` и `FreeLibrary`.|  
|\_wexecl \_wexecle \_wexeclp \_wexeclpe \_wexecv \_wexecve \_wexecvp \_wexecvpe \_execl \_execle \_execlp \_execlpe \_execv \_execve \_execvp \_execvpe \_spawnl \_spawnle \_spawnlp \_spawnlpe \_spawnv \_spawnve \_spawnvp \_spawnvpe \_wspawnl \_wspawnle \_wspawnlp \_wspawnlpe \_wspawnv \_wspawnve \_wspawnvp \_wspawnvpe \_wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|Эта функциональность недоступна для приложений UWP. Приложение UWP не может вызывать другое приложение UWP или классическое приложение.|Обходное решение отсутствует.|  
|\_heapwalk \_heapadd \_heapchk \_heapset \_heapused|Эти функции обычно используются для работы с кучей. Однако соответствующие API Win32 не поддерживаются в приложениях UWP. И приложения больше не могут создавать и использовать закрытые кучи.|Обходное решение отсутствует. Но функция `_heapwalk` доступна в DEBUG CRT для целей отладки. Их нельзя использовать в приложениях, загруженных в Магазин Windows.|  
  
 Следующие функции доступны в CRT для приложений UWP, но должны использоваться, только когда невозможно использовать соответствующие API Win32 или [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], например при переносе больших объемов кода.  
  
|||  
|-|-|  
|Однобайтовые строковые функции, например `strcat`, `strcpy`, `strlwr` и так далее.|Используйте в своих приложениях UWP только Юникод, поскольку все доступные API Win32 и [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] используют только наборы символов Юникода. Однобайтовые функции были сохранены для переноса больших объемов кода; в остальных случаях их следует избегать и по возможности использовать соответствующие функции для работы с расширенными символами.|  
|Функции ввода\-вывода потоков и ввода\-вывода файлов нижнего уровня, например `fopen`, `open` и так далее.|Эти функции являются синхронными, т. е. их не рекомендуется использовать в приложениях UWP. В приложениях UWP для открытия, чтения и записи файлов используйте асинхронные API, чтобы избежать блокировки потока пользовательского интерфейса. Примеры таких API можно найти в классе `Windows::Storage::FileIO`.|  
  
## Приложения для Магазина Windows 8.x и приложения Windows Phone 8.x  
 Помимо упомянутых ранее API, следующие API недоступны в приложениях Магазина Windows 8.x и приложениях Windows Phone 8.x.  
  
||||  
|-|-|-|  
|\_beginthread \_beginthreadex \_endthread \_endthreadex|Потоковые API Win32 недоступны в приложениях для Магазина Windows 8.x.|Вместо них следует использовать `Windows Runtime Windows::System::Threading::ThreadPool` или `concurrency::task`.|  
|\_chdir \_wchdir \_getcwd \_getdcwd \_wgetcwd \_wgetdcwd|Понятие рабочего каталога не применяется к приложениям для Магазина Windows 8.x.|Используйте полные пути.|  
|\_getpid|Эти функции устарели в предыдущих версиях CRT.|Используйте API Win32 `GetCurrentProcessId()`.|  
|\_isleadbyte\_l \_ismbbalnum, \_ismbbalnum\_l, \_ismbbalpha, \_ismbbalpha \_ismbbalpha\_l \_ismbbgraph \_ismbbgraph\_l \_ismbbkalnum \_ismbbkalnum\_l \_ismbbkana \_ismbbkana\_l \_ismbbkprint \_ismbbkprint\_l \_ismbbkpunct \_ismbbkpunct\_l \_ismbblead \_ismbblead\_l \_ismbbprint \_ismbbprint\_l \_ismbbpunct \_ismbbpunct\_l \_ismbbtrail \_ismbbtrail\_l \_ismbslead \_ismbslead\_l \_ismbstrail \_ismbstrail\_l \_mbsdup isleadbyte|Многобайтовые строки не поддерживаются в приложениях Магазина Windows 8.x.|Используйте вместо них строки Юникода.|  
|\_tzset|Переменные среды недоступны для приложений Магазина Windows 8.x.|Обходное решение отсутствует.|  
|\_get\_heap\_handle, \_heapmin|Соответствующие API Win32 не поддерживаются в приложениях Магазина Windows 8.x. И приложения больше не могут создавать закрытые кучи.|Обходное решение отсутствует. Но функция `_get_heap_handle` доступна в DEBUG CRT для целей отладки.|