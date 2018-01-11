---
title: "-Integritycheck-(требование проверки подписи) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bf86676ecbc37e346f538d180612f21352fb48b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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