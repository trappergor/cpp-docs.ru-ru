---
title: "/INTEGRITYCHECK (требование проверки подписи) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /INTEGRITYCHECK (требование проверки подписи)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, что цифровая подпись бинарного образа должна быть проверена во время загрузки.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## Заметки  
 По умолчанию **\/INTEGRITYCHECK** отключен.  
  
 Параметр **\/INTEGRITYCHECK** задает В заголовке PE исполняемого файла или файла DLL флаг для диспетчера памяти, требующий проверки цифровой подписи диспетчером памяти для загрузки образа в Windows.  Этот параметр следует установить и для 32 и 64\-разрядных разрядных библиотеки DLL, реализующие код, загруженный в режиме ядра Windows некоторыми функциями, и рекомендуется для всех драйверов устройств в Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/includes/winsvr08_md.md)] и [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)].  Версии Windows до Windows Vista игнорируют этот флажок.  Дополнительные сведения см. в разделе [Принудительная подпись целостности переносимых исполняемых файлов \(PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### Установка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно проекта **Страницы свойств**.  Для получения дополнительной информации см. [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Командная строка**.  
  
5.  В поле **Дополнительные параметры** введите `/INTEGRITYCHECK` или `/INTEGRITYCHECK:NO`.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Принудительная подпись целостности переносимых исполняемых файлов \(PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Пошаговое руководство о подписи кода в режиме ядра](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [DLL AppInit в Windows 7 и Windows Server 2008](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)