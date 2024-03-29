cmake_minimum_required(VERSION 3.14)
project(STM32F7 C)

set(CMAKE_C_STANDARD 11)

include_directories(CORE)
include_directories(HALLIB/STM32F7xx_HAL_Driver/Inc)
include_directories(HALLIB/STM32F7xx_HAL_Driver/Inc/Legacy)
include_directories(HARDWARE/LED)
include_directories(SYSTEM/delay)
include_directories(SYSTEM/sys)
include_directories(SYSTEM/usart)
include_directories(UCOSII/uC-CPU)
include_directories(UCOSII/uC-CPU/ARM-Cortex-M4/GNU)
include_directories(UCOSII/uC-CPU/ARM-Cortex-M4/IAR)
include_directories(UCOSII/uC-CPU/ARM-Cortex-M4/RealView)
include_directories(UCOSII/uC-LIB)
include_directories(UCOSII/uCOS-CONFIG)
include_directories(UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/GNU)
include_directories(UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/IAR)
include_directories(UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/RealView)
include_directories(UCOSII/uCOS-II/Source)
include_directories(UCOSII/UCOS_BSP)
include_directories(USER)

add_executable(STM32F7
        CORE/cmsis_armcc.h
        CORE/core_cm7.h
        CORE/core_cmFunc.h
        CORE/core_cmInstr.h
        CORE/core_cmSimd.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/Legacy/stm32_hal_legacy.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_adc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_adc_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_can.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_cec.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_conf_template.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_cortex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_crc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_crc_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_cryp.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_cryp_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dac.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dac_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dcmi.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dcmi_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_def.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dfsdm.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dma.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dma2d.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dma_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_dsi.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_eth.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_flash.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_flash_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_gpio.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_gpio_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_hash.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_hash_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_hcd.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_i2c.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_i2c_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_i2s.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_irda.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_irda_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_iwdg.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_jpeg.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_lptim.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_ltdc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_ltdc_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_mdios.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_nand.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_nor.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_pcd.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_pcd_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_pwr.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_pwr_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_qspi.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_rcc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_rcc_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_rng.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_rtc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_rtc_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_sai.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_sai_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_sd.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_sdram.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_smartcard.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_smartcard_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_spdifrx.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_spi.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_sram.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_tim.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_tim_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_uart.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_uart_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_usart.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_usart_ex.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_hal_wwdg.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_ll_fmc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_ll_sdmmc.h
        HALLIB/STM32F7xx_HAL_Driver/Inc/stm32f7xx_ll_usb.h
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_adc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_adc_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_can.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_cec.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_cortex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_crc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_crc_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_cryp.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_cryp_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dac.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dac_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dcmi.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dcmi_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dfsdm.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dma.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dma2d.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dma_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_dsi.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_eth.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_flash.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_flash_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_gpio.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_hash.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_hash_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_hcd.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_i2c.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_i2c_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_i2s.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_irda.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_iwdg.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_jpeg.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_lptim.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_ltdc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_ltdc_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_mdios.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_msp_template.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_nand.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_nor.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_pcd.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_pcd_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_pwr.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_pwr_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_qspi.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_rcc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_rcc_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_rng.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_rtc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_rtc_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_sai.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_sai_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_sd.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_sdram.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_smartcard.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_smartcard_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_spdifrx.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_spi.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_sram.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_tim.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_tim_ex.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_timebase_rtc_alarm_template.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_timebase_rtc_wakeup_template.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_timebase_tim_template.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_uart.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_usart.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_hal_wwdg.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_ll_fmc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_ll_sdmmc.c
        HALLIB/STM32F7xx_HAL_Driver/Src/stm32f7xx_ll_usb.c
        HARDWARE/LED/led.c
        HARDWARE/LED/led.h
        SYSTEM/delay/delay.c
        SYSTEM/delay/delay.h
        SYSTEM/sys/sys.c
        SYSTEM/sys/sys.h
        SYSTEM/usart/usart.c
        SYSTEM/usart/usart.h
        UCOSII/uC-CPU/ARM-Cortex-M4/GNU/cpu.h
        UCOSII/uC-CPU/ARM-Cortex-M4/GNU/cpu_c.c
        UCOSII/uC-CPU/ARM-Cortex-M4/IAR/cpu.h
        UCOSII/uC-CPU/ARM-Cortex-M4/IAR/cpu_c.c
        UCOSII/uC-CPU/ARM-Cortex-M4/RealView/cpu.h
        UCOSII/uC-CPU/ARM-Cortex-M4/RealView/cpu_c.c
        UCOSII/uC-CPU/cpu_core.c
        UCOSII/uC-CPU/cpu_core.h
        UCOSII/uC-CPU/cpu_def.h
        UCOSII/uC-LIB/lib_ascii.c
        UCOSII/uC-LIB/lib_ascii.h
        UCOSII/uC-LIB/lib_def.h
        UCOSII/uC-LIB/lib_math.c
        UCOSII/uC-LIB/lib_math.h
        UCOSII/uC-LIB/lib_mem.c
        UCOSII/uC-LIB/lib_mem.h
        UCOSII/uC-LIB/lib_str.c
        UCOSII/uC-LIB/lib_str.h
        UCOSII/uCOS-CONFIG/app_cfg.h
        UCOSII/uCOS-CONFIG/app_hooks.c
        UCOSII/uCOS-CONFIG/cpu_cfg.h
        UCOSII/uCOS-CONFIG/includes.h
        UCOSII/uCOS-CONFIG/lib_cfg.h
        UCOSII/uCOS-CONFIG/os_cfg.h
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/GNU/os_cpu.h
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/GNU/os_cpu_c.c
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/GNU/os_dbg.c
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/IAR/os_cpu.h
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/IAR/os_cpu_c.c
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/IAR/os_dbg.c
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/RealView/os_cpu.h
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/RealView/os_cpu_c.c
        UCOSII/uCOS-II/Ports/ARM-Cortex-M4/Generic/RealView/os_dbg.c
        UCOSII/uCOS-II/Source/os.h
        UCOSII/uCOS-II/Source/os_core.c
        UCOSII/uCOS-II/Source/os_flag.c
        UCOSII/uCOS-II/Source/os_mbox.c
        UCOSII/uCOS-II/Source/os_mem.c
        UCOSII/uCOS-II/Source/os_mutex.c
        UCOSII/uCOS-II/Source/os_q.c
        UCOSII/uCOS-II/Source/os_sem.c
        UCOSII/uCOS-II/Source/os_task.c
        UCOSII/uCOS-II/Source/os_time.c
        UCOSII/uCOS-II/Source/os_tmr.c
        UCOSII/uCOS-II/Source/ucos_ii.h
        UCOSII/UCOS_BSP/bsp.c
        UCOSII/UCOS_BSP/bsp.h
        UCOSII/UCOS_BSP/cpu_bsp.c
        USER/main.c
        USER/main.h
        USER/stm32f767xx.h
        USER/stm32f7xx.h
        USER/stm32f7xx_hal_conf.h
        USER/stm32f7xx_it.c
        USER/stm32f7xx_it.h
        USER/system_stm32f7xx.c
        USER/system_stm32f7xx.h)
