# Strata: a vertical status screen for the nice!view.
# It provides zmk_display_status_screen(), as does the stock nice!view widget,
# so CONFIG_NICE_VIEW_WIDGET_STATUS must be off.
if(CONFIG_NICE_VIEW_STRATA)
  if(CONFIG_NICE_VIEW_WIDGET_STATUS)
    message(FATAL_ERROR "CONFIG_NICE_VIEW_STRATA replaces the stock nice!view status screen; "
      "set CONFIG_NICE_VIEW_WIDGET_STATUS=n")
  endif()

  target_sources(app PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/src/strata/assets.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/strata/draw.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/strata/screen.c
  )
endif()
