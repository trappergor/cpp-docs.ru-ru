---
title: -Integritycheck-(требование проверки подписи) | Документы Microsoft
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
ms.openlocfilehash: 997e3f5bb79ee3cbfa95c5762b0d3e998c56f362
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (требование проверки подписи)
Указывает, что цифровая подпись двоичный образ будет выполняться проверка во время загрузки.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию **/INTEGRITYCHECK** отключен.  
  
 **/INTEGRITYCHECK** параметр наборов — в PE-заголовок файла DLL или исполняемого файла — флаг для диспетчера памяти для проверки цифровой подписи для загрузки изображения в Windows. Этот параметр должен быть установлен для 32-разрядных и 64-разрядных библиотек DLL, реализующие кода в режиме ядра, загруженного некоторыми компонентами Windows и рекомендуется для всех драйверов устройств в Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/reference/includes/winsvr08_md.md)], и [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)]. Версии Windows, предшествующей Windows Vista игнорировать этот флаг. Дополнительные сведения см. в разделе [Принудительная целостность подписи из Portable Executable (PE) файлов](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **командной строки** страницу свойств.  
  
5.  В **Дополнительные параметры**, введите `/INTEGRITYCHECK` или `/INTEGRITYCHECK:NO`.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Принудительная целостность подписи из Portable Executable (PE) файлов](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Подписи пошаговом руководстве кода в режиме ядра](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Библиотеки DLL в Windows 7 и Windows Server 2008](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)