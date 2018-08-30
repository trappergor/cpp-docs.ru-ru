---
title: -INTEGRITYCHECK (требование проверки подписи) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acc43bc4175f42282014e94426717527143dc059
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197060"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (требование проверки подписи)
Указывает, что цифровая подпись бинарного образа должна быть проверена во время загрузки.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию **/INTEGRITYCHECK** отключен.  
  
 **/INTEGRITYCHECK** наборы параметров, в заголовке PE исполняемого файла или файла DLL, флаг для диспетчера памяти для проверки цифровой подписи для загрузки образа в Windows. Этот параметр, должно быть задано для 32-разрядных и 64-разрядных библиотек DLL, реализующих кода режима ядра, загруженного некоторыми компонентами Windows и рекомендуется для всех драйверов устройств в Windows Vista, Windows 7, Windows 8, Windows Server 2008 и Windows Server 2012. Версии Windows до Windows Vista игнорируют этот флажок. Дополнительные сведения см. в разделе [принудительно целостности подписи из переносимых исполняемых (PE) файлов](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **командной строки** страницу свойств.  
  
5.  В **Дополнительные параметры**, введите `/INTEGRITYCHECK` или `/INTEGRITYCHECK:NO`.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Принудительная целостность подписи из переносимых исполняемых (PE) файлов](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Пошаговое руководство о подписи кода режима ядра](https://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Библиотеки DLL инициализации приложений в Windows 7 и Windows Server 2008](https://msdn.microsoft.com/windows/hardware/gg463040.aspx)