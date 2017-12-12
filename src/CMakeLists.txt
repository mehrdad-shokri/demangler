
add_subdirectory(demangler)
if(DEMANGLER_TOOLS)
	add_subdirectory(demangler_grammar_gen)
	add_subdirectory(demanglertool)
endif()
