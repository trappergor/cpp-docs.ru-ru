---
title: /INTEGRITYCHECK (требование проверки подписи)
ms.date: 11/04/2016
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
ms.openlocfilehash: 1732c612501b66753635b272f94764975c555f75
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492851"
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (требование проверки подписи)

Указывает, что цифровая подпись двоичного образа должна проверяться во время загрузки.

```
/INTEGRITYCHECK[:NO]
```

## <a name="remarks"></a>Примечания

По умолчанию **/INTEGRITYCHECK** отключен.

Набор параметров **/INTEGRITYCHECK** — в заголовке PE файла DLL или исполняемого файла — флаг, который диспетчер памяти проверяет на наличие цифровой подписи, чтобы загрузить изображение в Windows. Этот параметр должен быть установлен как для 32-разрядных, так и для 64-разрядных библиотек DLL, которые реализуют код режима ядра, загружаемый определенными компонентами Windows, и рекомендуется для всех драйверов устройств в Windows Vista, Windows 7, Windows 8, Windows Server 2008 и Windows Server 2012. В версиях Windows, предшествовавших Windows Vista, этот флаг не учитывается. Дополнительные сведения см. в разделе [Принудительная проверка подписывания переносимых исполняемых файлов (PE)](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).

### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните узел **Компоновщик**.

1. Выберите страницу свойств **Командная строка** .

1. В окне **Дополнительные параметры**введите `/INTEGRITYCHECK` или `/INTEGRITYCHECK:NO`.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[Принудительная целостность подписывания переносимых исполняемых файлов (PE)](https://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)<br/>
[Требования к подписывания кода в режиме ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)<br/>
[Библиотеки DLL и безопасная загрузка](/windows/win32/dlls/secure-boot-and-appinit-dlls)
