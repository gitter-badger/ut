#
# Copyright (c) 2019 Kris Jusiak (kris at jusiak dot net)
#
# Distributed under the Boost Software License, Version 1.0.
# (See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt)
#
function(benchmark name file)
  add_executable(b${name} ${file}.cpp)
  target_compile_options(b${name} PRIVATE ${ARGN})
  add_custom_command(TARGET b${name} COMMAND b${name})
endfunction()

benchmark(expect_udl expect "-DEXPECT_UDL")
benchmark(expect_that expect "-DEXPECT_THAT")
benchmark(expect_eq expect "-DEXPECT_EQ")
benchmark(include include)
benchmark(suite suite)
benchmark(test test)
