﻿# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),

## [Unreleased]

### Added
### Fixed
### Changed
### Removed

## [20.39.3] - 2024-08-07

### Removed

- Removed C++11 restriction on `etl::observer::notification`

### Changed

- [#946](https://github.com/ETLCPP/etl/issues/946) Make include paths to private files relative

### Fixed

- [#917](https://github.com/ETLCPP/etl/issues/917) `unaligned_type` doesn't compile with floating point types

## [20.39.2] -

- Removed `EmbeddedTemplateLibrary-20.39.0.tar.gz` from project.


~~~~
===============================================================================
20.39.1

Fixes:
#940 Allow etl::observer notification without argument
     Added a void specialisation to the < C++11 code.
#942 Warning on pragma c++20-compat

Updates:
Added etl::count_of, etl::has_duplicates, etl::has_duplicates_of

===============================================================================
20.39.0

Refactored:
Breaking change.
Modified io_port classes so that they are not derived from iterator types.
    Added iterator and const_iterator types.
    Added iter() and citer() member functions to get an iterator.
    Added &= |= ^= <<= >>= and ~ operators (only available for io_port_rw and io_port_wos types)
    Added static asserts to only allow integral types.

Fixes:
#921 unique_ptr reset
#923 Missing equality operator for class expected 
#930 Unused parameter warnings
#931 Using etl::make_vector to make a vector of two pairs causes a compile error

Features:
#918 Request for additional operator support for etl::io_port_*
#919 callback_timer: expose callback_timer_data::is_active() as icallback_timer public method 
#920 Define ETL_USING_LEGACY_VARIANT as a convenience macro for code that tries to support both new and legacy variants
#940 Allow etl::observer notification without argument

Pull Requests
#905 Add-support-for-type_identity
#909 fix c++20-compat false positive
#914 Fix doc comment for pool::allocate()
#924 Add an etl::nullptr_t type to <etl/nullptr.h>
#925 Add equality operators for class expected
#926 Fix issue #923 equality operator for class expected
#927 Fix missing partial specialisation equal operators
#928 Add missing swap implementations for expected
#929 Fix run-tests.sh script
#932 Fix issue #931 Using etl::make_vector to make a vector of two pairs causes a compile error
#934 Fixes compiler detection with Wundef
#935 Added 20 bit integral limits (MSP430 devices)
     New configuration macro, ETL_USE_20BIT_TYPES, which controls the definition of ETL_USING_20BIT_TYPES and ETL_NOT_USING_20BIT_TYPES.
#939 Fix histogram indexing when accessed via operator[]

===============================================================================
20.38.17

Fixes:
#895 Removed std algorithm calls from algorithm.h

Features:
Added Base64 codecs. RFC2152, RFC3501, RFC4648 and RFC4648-URL
Added parameter_type_t for C++11

Pull Requests:
#905 Added support for type identity

Other:
Reenabled address sanitizer for VS2022

===============================================================================
20.38.16

Fixes:
#889 bitset_new.h throws warnings for GHS compiler
     Fixed ordering of static & ETL_CONSTEXPR14.
#895 Removed std algorithm calls from algorithm.h

Changes without a GitHub issue#:
Added extra tests for as_bytes and as_writable_bytes
Made conversion operator for C++03 etl::byte public

===============================================================================
20.38.15

Fixes:
#892 Compilation Error with constexpr in etl::string_base::size() on ESP-WROVER-KIT (c++11)
     Removed ETL_CONSTEXPR from etl::string_base::size().
     Also removed ETL_CONSTEXPR from etl::vector::size().

===============================================================================
20.38.14

Features:
Added GCD and LCM algorithms. etl::gcd and etl::lcm
Added specialisations of etl::rotate for different iterator types
Added ETL_NODISCARD, ETL_CONSTEXPR14 and ETL_NOEXCEPT to etl::absolute and etl::absolute_unsigned

===============================================================================
20.38.13

Fixes:
Revert change #804 to restore value initialisation of type0 for default constructor

===============================================================================
20.38.12

Fixes:
#815 etl::remove_if calls predicate twice for first iterator, where predicate returns true.
#885 queue move-assignment is not compiling
Modified UnitTest++ SUITE macro for better VS2022 intellisense compatibility

===============================================================================
20.38.11

Fixes:
#803 etl::unordered_map buffer overflow
#805 legacy etl::bitset set/reset does not work if the element type is greater than 8 bit
#815 etl::remove_if calls predicate twice for first iterator, where predicate returns true.
#819 etl::optional cannot return an optional object of self from member function
#820 etl::send_message does not allow for non-virtual calls
#825 Fixed extent etl::span shouldn't allow default constructor
#827 Declaration order for etl::first_set_bit_position in binary.h
#829 Possible bug on assign of etl::array
#830 gcc warning - potential null pointer dereference using etl::map
#845 etl::message_packet missing a copy constructor
#857 etl::expected emplace methods are missing-return
#868 etl::variant is missing comparison operators
#869 etl::fsm::receive function can call p_state process_event also when p_state is nullptr
#873 Validate allocated DataNode is not null to prevent gcc Wnull-dereference
#874 Allow direct removal of a node from an etl::intrusive_list
#877 Optimize find_first_not_of and find_last_not_of on string_view
#879 Render include paths relative (limits.h & random.h)
#855 Strange expression in volatile atomic operator--

Pull Requests:
#782 Set is full error when adding existing item                              (İsmail Tüzün)
#804 etl::variant (variadic) default constructed state                        (Manuel Seeböck)
#812 Implement SAE-J1850 CRC8                                                 (Drew Rife)
#832 Only copy/move storage value when optional is valid                      (Chiraffollo)
#843 In subspan function, add static checks on extents                        (mike919192)
#849 Fix string_stream add missing initializations of const format specifiers (Manuel Knörle)
#850 Fixed names according to Arduino's guidelines                            (Mipsters)
#854 In-place construction of shared message                                  (SanderSmeenkInspiro)
#858 Fix unique_ptr assigning nullptr to a null unique_ptr causes an assert   (Derek Ludwig)
#861 Implement constexpr strong typedef                                       (Drew Rife)
#862 Update ETL_CONSTEXPR and C++14 designation from type_def                 (Drew Rife)
#863 Add eq and ne operators for compare utility                              (Benzinnos)
#865 Add utils compare equality operator                                      (Benzinnos)
#879 Make include paths to private files relative                             (David Hebbeker)

Features:
#774 Truncating access for etl::bitset - Added extract() functions.
#806 etl::variant_pool should support C++17 variadic parameters (supports C++11 variadic parameters)
#812 Implement-SAE-J1850-CRC8
#818 Apply-code-spell-check-across-entire-code-base
#841 Change push to push_back on containers, so they can be used with std::back_inserter. Added push_insert_iterator
#847 Add has_active_timer to callback_timer
#883 Add etl::partition and etl::nth_element algorithms
#864 cyclic_value first/last methods. Make first() and last() static for template based limits specialisation

Changes without a GitHub issue#:
Added etl::mem_fn (clone of std::mem_fn)
Added etl::generate algorithm (clone of std::generate)
Added binary functors for ~ & | ^
Added etl::is_default_constructible & etl::is_default_constructible_v
Added syntax checks to GitHub CI
Refactored etl::optional implementation
Fixed etl::optional operator =() for invalid values with non-pod types
Refactored message_packet constructors
Added specific copy and move constructors to message_packet for C++17 and above.
Changed optional 'simple' types implementation for C++14 constexpr compatibility
Fixed implicitly disabled copy constructor for message_packet
Modified accepts() message router functions to interrogate subscribed and successor routers to achieve consistency.
Fixed 'nodiscard' keyword errors
Removed unused ETL_STATIC_CONSTANT
Make binary functor operator() const
Improved display of CHECK_EQUAL_HEX in UnitTest++

===============================================================================
20.38.10
#800 Prioritize ETL_TARGET_OS_* for mutex selection

===============================================================================
20.38.9
Added etl::crc1 (parity)
#799 Iterator returned by crc.input() does not satisfy std::output_iterator

===============================================================================
20.38.8
#795 etl::private_variant doesn't fully respect the chosen error reporting.
#797 Undeclared FP_NAN, FP_INFINITE and FP_ZERO

===============================================================================
20.38.7
Updated CI scripts
Refactored GitHub CI workflows
Updated build script text
Added additional etl::make_lsb_mask and etl::make_msb_mask binary functions
#779 hash.h: warnings produced with -Wfloat-equal
#781 etl::multi_span::iterator::operator *() fails if first span is empty
#780 endian enum_type produces useless-cast warnings
#783 Cannot insert existing value to full set
#786 u8string
#787 etl::expected doesn't compile with ETL_LOG_ERRORS

===============================================================================
20.38.6
#777 Allow Building Tests as Submodule and GCC < 11
Refactored etl::itr_swap for maximum efficiency.

===============================================================================
20.38.5
#776 Add missing semicolons

===============================================================================
20.38.4
#773 Return raw pointer for etl::multi_span::operator->()

===============================================================================
20.38.3
#767 etl::pool silently produces unaligned allocations for types with stricter alignment requirements than built in types 

===============================================================================
20.38.2
#749 Code change causes warning with armcc compiler
#753 IAR's overload resolution struggles with etl::span::span(etl::array&)
#754 ambiguous etl::bit_stream_reader::bit_stream_reader() for some etl::span
#755 warning about constexpr in array.h
#756 Parameter pack compilation error
#758 Move assignment not working for non-empty containers
#761 Make "private" includes relative
#765 etl::optional cannot be constexpr
#766 etl::unique_ptr::reset() can call deleter with nullptr argument 
Re-enabled bit_stream_writer tests

===============================================================================
20.38.1
Deleted

===============================================================================
20.38.0
#696 fsm/hfsm self-transitions
#702 etl::message not trivially_copyable
#744 Feature request: Get time when next timer will expire etl::callback_timer
#745 Assertion triggered in hash.h when compiling for MSP430
#746 Missing etl::legacy::variant overload of emplace with 0 Arguments
#748 armcc error on vector::insert
Fixed unexpected pool release behavior when the pool is empty
Added C++03 compatible etl::move and etl::move_backward
Allow C++03 delegate in etl::callback_timer
Change to require semicolons after debug count macros
Re-enabled tests for etl::string_ext
Removed redundant #includes
Added MutexMessageRouter example

===============================================================================
20.37.3
#737 etl::equal specialisation for etl::span is deduced wrongly when using STL and CPP20. Added C++20 four iterator std::equal variants.
#738 etl::expected assignment operator won't work when TValue and TError are the same type. Changed assignment from etl::unexpected to use variant::emplace instead of direct assignment.
#739 Could not compile ETL with gcc 9.4.0 (C++11). Added compatibility for GCC-9 + C++11. Added missing return reference from emplace member function int variant_variadic.h
Removed many -02 warnings for GCC-13

===============================================================================
20.37.2
#733 Fix etl::expected assignment from etl unexpected.
#734 Add missing new line at end of files.
#735 fix(minmax): fix bug in minmax include mismatch detection.

===============================================================================
20.37.1
#723 Added missing final CR/LF to result.h.
Fixed etl::optional arrow and dereference operators.
Enhanced min/max push/pop headers. Detects mismatched header includes.

===============================================================================
20.37.0
#708 Fix missing class key with friend.
#709 intrusive_list::iterator operator -> should not dereference pointer before return.
#710 Calling accept on etl::variant visits a copy instead of the original object.
#711 Added etl::is_forward_link, etl::is_bidirectional_link and etl::is_tree_link to intrusive links.
     Added Constructors, access and status member functions to intrusive links.
#712 Unable to use etl::optional with non-default-constructible POD objects.
#716 etl::variant (variant_varadic) default constructed state
#720 etl::optional rvalue value_or() broken
#722 Bitset accesses memory out of bounds
#725 variant_pool create method should use std::forward
Modified etl::visitor to allow direct specification of the argument type.
Added etl::is_visitor trait.
Removed default link type for etl::intrusive_list and etl::intrusive_forward_list

===============================================================================
20.36.2
#707 parameter_pack: Fix C++17 pedantic build

===============================================================================
20.36.1
#700 Compilation error for [] map operator. Fixed map const placement new issue.
Re-enabled memcast tests.

===============================================================================
20.36.0
#663 Make unit tests compile for C++20
#675 Compilation error in optional.h
#684 Added sanitization fix for MinGW
#687 Build failure. constexpr keyword before template keyword 
#689 Add as_bytes and as_writable_bytes
#690 Add rvalue accessors to expected and optional and update constructors
#692 operator [] for flat_map always calls default constructor for mapped_type
#695 Visiting a const variant (variadic)
#698 Behaviour of bidirectional_link nodes. Links are now cleared when unlinked
#699 Optional(POD) operator bool explicit
Optimised map/flat_map/unordered_map [] operator and insert()
Removed [] operator for reference_flat_map
Unit tests compile for C++11
Fixed C++11 constexpr compatibility
Removed redundant 'const' in template parameters
Updated CI scripts to enable C++ standard and optimisation selection
Updated static constant definitions
Fixed incorrect return types for reverse iterator begin() & end()
Updated C++ standard conditional compilation for reverse iterator functions
Fixed latest Address Sanitizer issues
Message packet unused parameter fix
Added ETL_OR_STD17 macro as the namespace for size()
Added Tasking compiler
Fix type traits generator
Fix test array sizes
Changed some ETL_ASSERT macros to ETL_ASSERT_OR_RETURN
Updated CMake files to allow C++ standard selection
Replaced ETL_ASSERT_AND_RETURN with ETL_ASSERT_OR_RETURN
Changed native char8_t check
Renamed Github vs2022.yml to visual-studio.yml
Updated Unittest++ checks
Comments and noexcept updates to placement new
etl::variant (variadic) refactor and updates for C++ standards compatibility
etl::overload available in C++17 only
map/flat_map speed optimisations
Various C++03 compatibility updates for maps
Refactored Bash compilation scripts to allow selection of C++ standard and optimisation level
Renamed Bash compilation scripts. Changed 'sanity checks' to 'syntax checks
Some internal constant case changes from all upper to capital case

===============================================================================
20.35.15
#627 Make tests build with C++14
#663 Make unit tests compile for C++20
#675 Compilation error in optional.h line 405

===============================================================================
20.35.14
Convert the Visual Studio project to VS2022

===============================================================================
20.35.13
#649 Fixed the false positive 'array-bounds' errors for ETL unit tests.
#652 Fixed false positives 'maybe-uninitialized' errors for ETL unit tests.
Moved virtual functions in etl::fixed_sized_memory_block_allocator from 'private' to 'protected'. 

===============================================================================
20.35.12
#615 Addition of etl::expected
#649 Changed intrusive_list and intrusive_forward_list iterator constructor parameter from reference to pointer.
#667 etl::span copy constructor with original span with fixed extent causes pend iterator to be invalid
#668 byte_stream changes that add error exceptions have changed previous behaviour
#670 span equality operators
#672 HFSM-specific start() and reset()
Fixed span templated copy constructor
Added destination_router_id parameter overrides to receive() virtual functions
Added ""_sv string view operators
Added M17 CRC
Added repair() to etl::circular_buffer
Added etl::contruct_object_at, etl::get_object_at and etl::destroy_object_at
Added etl::is_aligned, etl::alignment_exception and etl::alignment_error
Removed unnecessary code in etl::vector_ext::repair()
Updated sanity check make files
C++03 compatibility improvements

===============================================================================
20.35.11
Added emplace by index to variant (variadic)
#660 byte_stream_reader::skip error

===============================================================================
20.35.10
#659 emplace member functions return reference to emplaced value

===============================================================================
20.35.9
#657 -Wpedantic-failure. Removed superfluous semicolons
#653 CMake - Don't warn on tag missing when subproject
#651 result<T, void> specialization
#650 Fix result<void, E> default ctor
Removed Ubuntu 18.04 from Github Actions
Added Ubuntu 22.04 to Github Actions

===============================================================================
20.35.8
#648 Improve is_constructible, is_copy_constructible, is_move_constructible for type traits with default definitions 
#645 Avoid 'missing return statement at end of non-void function' in `etl::visit<>()`.
Removed unused ETL_USE_MEM_BUILTINS option

===============================================================================
20.35.7
Updated etl::delegate to handle const functors correctly

===============================================================================
20.35.6
#643 Don't use push_macro and pull_macro with Tasking compiler

===============================================================================
20.35.5
#641 Wrong usage of enable_if for none C++11 compilers

===============================================================================
20.35.4
#639 Only build tests if top level project

===============================================================================
20.35.3
#636 Fix bug in optional emplace for pod type specialisation

===============================================================================
20.35.2
#634 Strange behavior in move assignment of optional

===============================================================================
20.35.1
#628 Fixed set of ETL_NO_STL flag in meson.build
#631 unique_ptr derived copy or move to base does not compile
Removed duplicate include in etl::array_view

===============================================================================
20.35.0
#596 Helper functions to convert strings to numeric values. etl::to_arithmetic
#600 Fix 'maybe-uninitialized' g++ error on macros
#601 Move __STDC_LIMIT_MACROS and __STDC_CONSTANT_MACROS before `#include <stdint.h>`
#602 Replace ETL_COMPILER_ICCAVR by ETL_COMPILER_IAR
#603 Add back/front insert iterator
#604 Update-test-sources-in-meson-build
#605 Special case check for hashing -0.0
#606 Fix non-usage of key equal function
#610 Added select1st and select2nd
#612 Automatically detect native endianness for IAR compiler platform
#613 Fix bare assert in reference_counted_object.h
#614 unaligned types: use unsigned storage type
#615 Addition of etl::expected (partial). Implementation of etl::unexpected
#616 Provide cmake library for UnitTest++
#618 fix bug in find_next of (new) bitset class
#621 No need to initialize the C-compiler, small speed improvement
#626 Empty etl::optional ctor storage initialization performance
Removed constexpr for etl::bit_cast due to unreliability of compiler support
Added has_value() as an alias for is_value() for etl::result (consistency with STL conventions)
Added ETL_ERROR_WITH_VALUE macro for exceptions that require a value
Changed scaling template parameter for etl::scaled_rounding to uint32_t
Remove redundant etl::pair functions
Updated string_view and char traits

===============================================================================
20.34.0
Changed explicit message constructor for unsupported message types
Added etl::circular_iterator and circular iterator extensions to etl::span
Added etl::bitset_ext
Added etl::lsb_mask, etl::make_lsb_mask, etl::msb_mask and etl::make_msb_mask to binary utilities
Updates for unordered maps and sets for an API that better matches the STL
Fixes for etl::result<void, TError>
Deleted copy constructors for etl::circular_buffer_ext, etl::indirect_vector_ext and etl::vector_ext to eliminate dangling pointers
Fix non-C++03 code syntax
Fixed unordered container equality tests to match STL
#581 Hash function for enums
#583 Permit non-default-constructable hashes and key-equals
#584 unordered_set::const_iterator has incorrect value_type
#585 Fixed etl::result<void> being unusable due to deleted default constructor
#587 Fixed IAR build warnings in message_packet
#589 Add minmax_push.h/minmax_pop.h includes
#593 Workaround for __has_include(<...>) and ICCAVR
#591 Automatically define __STDC_LIMIT_MACROS and __STDC_CONSTANT_MACROS

===============================================================================
20.33.0
Added etl::message_broker to message framework
Added 'successor' parameter constructors to all etl::imessage_router derived classes
Added etl::binary_search to algorithm.h
Standardise conditional compilation macros for ETL_USING_CPP11 and ETL_USING_STL
#546: Added a new variant of bitset that may be constexpr
Removed the use of ETL_FORCE_CONSTEXPR_ALGORITHMS as all algorithms may be constexpr
Rationalised etl::send_message functions
Fixed implicit virtual warning for etl::vector
Fixed C++03 delegate compatibility
Added missing char_traits unit tests and char_traits bug fixes
Added default message id constructors
Added ability to set the bitset from wchar_t, char16_t and char32_t
Added ARM5 and ARM6 compiler compatibility for GCC atomics
#579: Fixed Unexpected namespace for variant with non-CPP11 compiler

===============================================================================
20.32.1
Added size only constructor, set_buffer() and is_valid() members to circular_buffer_ext

===============================================================================
20.32.0
#571 Activate GCC and clang compiler warnings
#575 Bip buffer improvements
#576 Invoke function pointers with parenthesis
#574 Allow users to remove SYSTEM keyword because it forces C linkage for some gcc versions

===============================================================================
20.31.3
#569 Fixed swap function for circular_buffer_ext
#568 Fixed circular_buffer iterator -> operators
Optimised container move for external buffers
Added functions and macros to etl::debug_count
Added tests for error handler macros

===============================================================================
20.31.2
#567 error-handler: only return when the condition is false 

===============================================================================
20.31.1
Addition of extra ETL_NODISCARD and ETL_NOEXCEPT to etl::span & etl::poly_span.
Fixed warnings for initialisation order for some etl::poly_span constructors.

===============================================================================
20.31.0
Added etl::poly_span
Refacted parts of etl::span, including prevent compound statements in constexpr methods for C++11
Added etl::is_enum

===============================================================================
20.30.1
Fixed #560 Unable to upcast legacy variant Latest
Refactored legacy variant to remove upcast functors.
Added upcast_ptr, is_base_of & 'not a base' error exception to legacy variant.
If ETL_USE_LEGACY_VARIANT is defined then legacy variant is in the etl namespace.
If ETL_USE_LEGACY_VARIANT is not defined then legacy variant is in the etl::legacy namespace.
Added non-member etl::send_message for etl::shared_message
Green Hills compiler compatibility

===============================================================================
20.30.0
Fixed #560 Unable to upcast legacy variant.
Refactored legacy variant to remove upcast functors.
Added upcast_ptr, is_base_of & 'not a base' error exception to legacy variant.
If ETL_USE_LEGACY_VARIANT is defined then legacy variant is in the etl namespace.
If ETL_USE_LEGACY_VARIANT is not defined then legacy variant is in the etl::legacy namespace.
Added non-member etl::send_message for etl::shared_message

===============================================================================
20.29.3
Updated message_packet_generator.h to match etl::message_packet changes.

===============================================================================
20.29.2
#557 QueuedFSM example does not compile.

===============================================================================
20.29.1
Added etl::byte_stream_overflow assert to byte_stream_reader 'skip'.

===============================================================================
20.29.0
Added etl::bit_stream_writer
Added etl::bit_stream_reader
Deprecated etl::bit_stream
Added callback option to etl::byte_stream_writer
Added error exceptions to byte_stream_writer
Added ETL_NODISCARD to etl::delegate 'create' and 'is_valid' functions
Added etl::visit support to etl::variant
Refactored C++17 message_packet
Refactored etl::atomic implementations to allow non-(integrals/pointers/bool)
Refactors etl::vector and etl::deque resize() to take const reference parameter
Renamed ETL_ALWAYS_ASSERT to ETL_ASSERT_FAIL
Removed duplicate void_t definition
Removed duplicate etl::declvar definition
Renamed cumulative_moving_average to pseudo_windowed_moving_average to more accurately reflect its algorithm.
Changed etl::debounce internal state names to avoid clashes with Arduino macros.

===============================================================================
20.28.0
Fixed issues raised by sanitizer.
Added conditional compilation for 8 bit type in hash.h
Fixed warnings for 64bit compilation.
Fixed sanity check includes.
Fixed incorrect returned span length for byte stream read.
Updates to etl::successor and derived classes.

===============================================================================
20.27.3
#531 Fixed: Compilation of etl::reference_counted_message_pool with ETL_LOG_ERROR 
enabled due to non-public inheritance.

===============================================================================
20.27.2
Added scripts to automatically update version information.
Added ETL version information to etl::traits.
Small optimisations for computing indexes for queues & cyclic_value.
#530 Fixed: etl::nth_type not implemented correctly.
#521 CMake: Add package version file for installation.
#525 Fixed: plusplus constant type.
#517 Fixed: unused-local-typedefs warning.

===============================================================================
20.27.1
Fixed undefined macros when compiler type is defined by the user.

===============================================================================
20.27.0
Added etl::functor for wrapping global/static functions in a functor.
Added etl::member_function_wrapper for converting a member function to a static function.
Added etl::functor_wrapper for converting a member function operator to a static function.

===============================================================================
20.26.0
Added constexpr support for etl::unaligned_type.
Added etl::traits namespace containing traits mirroring many ETL macros.
Traits are const for C++03, constexpr for C++11 and above.
Removed some uses of GCC builtins due to compatibility with constexpr.
etl::swap is now ETL_CONSTEXPR14.
Changed ETL_ENDIANNESS_IS_CONSTEXPR to ETL_HAS_CONSTEXPR_ENDIANNESS.
Changed ETL_CONSTEXPR17 to ETL_CONSTEXPR14 for reverse iterators
Added template wrappers around memcpy, memmove, memcmp, memset& memchr.
The counter in etl::debug_count is atomic, if available.
Embedded essential UnitTest++ source into the project, as it is no longer maintained on GitHub.

===============================================================================
20.25.0
Added message_timer_interrupt
Added callback_timer_interrupt
Changed message_timer_atomic and callback_timer_atomic to require an atomic counter template type.
Added extra condition compile macros to control std::initializer_list.
Initializer list tests are in a separate project.
Modified etl::instance_count to take an optional counter type.
Renamed Arduino files to stop PlatformIO getting confused.
Changed from C cast to C++ cast in memory.h
Always use stddef.h
Modified WCHAR_MIN and WCHAR_MAX checks.
Added char8_t type.
Fixed 'unused function parameter' warnings.

===============================================================================
20.24.1
callback and message timers now use etl::timer_semaphore_t instead of et::atomic_uint_least16_t
Fixed send_message function signatures.

===============================================================================
20.24.0
#503 Algorithm transform uses expensive post increment operator - Fixed for all occurrences of iterator increment.
#504 ETL_CONSTANT vs const in binary.h - Fixed.
Many algorithms will leverage built-ins, if available. Dependent on compiler version.
Added detection or selection of built-ins.
Much of etl::string and etl::string_view can be constexpr.
Added ETL initializer_list implementations that are compatible with major compilers.
Added etl::construct_at support.
Added etl::byte

===============================================================================
20.23.0
Recoded state_chart to reduce its resource requirements.
Added compile time state chart variants.
Added etl::unaligned_type for fundamental types.
Added reverse engineered functionality from C++20 <bit>.
Added all permutations of leading/trailing bit tests.
Changed inline functions to templates in binary.h.
Added etl::midpoint and etl::lerp
Recoded etl::endian & etl::endianness to allow constexpr in certain configurations.
Updates and fixes to etl::bitset. Added to_ulong, to_ullong, to_string member functions.
Moved void_t definition.
Renamed 8bit check macro.
Updated tests to support C++20 STL.
Modified C++ language level detection.
Added all permutations of leading/trailing bit tests.
etl::iterator is more SFINAE compatible.
Updated C++ standard detection.

===============================================================================
20.22.0
Split callback and message timer to atomic and locked interrupt versions.
#480 Fixed: Double formatting with precision > 9
#481 Fixed: etl::span const data cannot be created from non const c array of data.
#482 Fixed: Two or more etl::span/array_view of different types create ambiguous overloading set 
#483 Fixed: Added Green Hills compiler to minmax push and pop.
#484 Fixed: etl::vector test_uninitialized_resize_excess not calling uninitialized_resize.
#485 Fixed: etl::message_packet takes message types that are not in its list.

===============================================================================
20.21.0
Added contains() method to etl::map and etl::set + variants.
Added support for transparent comparators.
When ETL_NO_ATOMICS is defined the timer.h file does not define timer_semaphore_t.
etl::deque::resize throws etl::deque_full instead of etl::deque_out_of_bounds, if requested size is too large.

===============================================================================
20.20.0
Updated container 'insert' and 'erase' to C++11 style const_iterator parameters. (#463)
Fixed container template function overload ambiguity. (#466)
Harmonize copy ctor and assignment for etl::delegate. (#465)
Added constexpr support for etl::enum_type. (#462)
Added 'make' functions to construct containers.
Remove unnecessary casts that causes warnings. (#461)
Added non-const string pointer overload. (#449)
Changed != to < in etl::ipool to get rid of erroneous clang-tidy nullptr dereference warning. (#457)
Added ifdef guard for MSVC pragma (#455)

===============================================================================
20.19.0
Updates to etl::delegate. Added more constexpr and set() functions.
Removed conanfile.py. Now controlled by conan repository.
Fixed missing 'typename' keyword in etl::multi_span.
Added missing explicit initialisation from in_place structures.
Fixed hidden parameter warning in unordered_map, unordered_multimap, unordered_set, unordered_multiset.
Disable etl::begin(), etl::end() and  etl::size() for STL & >= C++11.
Add available_bytes to byte_stream_reader & byte_stream_writer.
Meson tests & style fix (#447).
Fix constexpr accepts() implementation to be C++11 compliant (#451, #452)
Fix-compiler-error-msvc-16 #454

===============================================================================
20.18.1
Added missing 'start, length' read() variants for byte_stream_reader.
Added multi_span to 'sanity checks'.

===============================================================================
20.18.0
Added front() access to locked queues.
Added .clang-format rules.
Added etl::pool_ext and etl::generic_pool_ext.
Added etl::multi_span.
Added CMSIS RTOS2 mutex variant.
Added 'unchecked' read and write members functions to byte_stream_reader and byte_stream_writer.
Fixed byte_stream_reader to be able to use const buffers.
Removed compiler warning messages.
Fixed missing 'public' access for message_router_registry iterator.

===============================================================================
20.17.3
Modified etl::cyclic_value for ARMCC v5 compatibility

===============================================================================
20.17.2
Replaced std::size_t with size_t in etl::in_place_index

===============================================================================
20.17.1
Added successor handling for accepts()
Added successor handling for pre-C++17 message router

===============================================================================
20.17.0
Added etl::result type
Added etl::byte_stream
Added denominated etl::to_string overloads
Added etl::remove_cvref to type traits
Replaced etl::remove_reference_t with etl::remove_cvref_t in variadic etl::variant
Added call_if and call_or member functions to etl::delegate
Improved compliance with MISRA rules
Extended 'successor' handling for all derived message router types

===============================================================================
20.16.2 
Fixed incomplete template specialisations in type_traits.h for C++11

===============================================================================
20.16.1
Fix for etl::mutex::try_lock() for GCC

===============================================================================
20.16.0
Added C++17 variadic versions of etl::message_router and etl::fsm
'pop_into' in queue and stack will move if possible.
Added Force C++03 option to Github CI
Expanded compiled variants for scripts

===============================================================================
20.15.1
Fixed etl::fsm C++03 template definition that was corrupted in 20.10.0
Fixed meson.build

===============================================================================
20.15.0
Added a Bipartite buffer, by Benedek Kupper.
etl::bip_buffer_spsc_atomic
notify_observers() takes universal reference for C++11 and above.
Updated type traits generator.

===============================================================================
20.14.1
Changed std::forward to etl::forward in etl::variant (variadic)

===============================================================================
20.14.0
Added a variadic version of etl::variant. Usable for C++11 and up.
Added etl::overload pattern class. Groups lambdas into a functor class.
Refactored type_traits.h. Uses STL, compiler built-ins or user defined specialisations, dependent on settings.
Added etl::conditional_t to type_traits.h
Added etl::conjunction and etl::disjunction to type_traits.h
Added etl::integer_sequence to utility.h
Added etl::in_place, etl::in_place_t and etl::in_place_index_t.
Fixed missing etl::alignment_of specialisation for const void.

===============================================================================
20.13.0
Added a specialisation of etl::delegate_service to allow constexpr service.

===============================================================================
20.12.0
Added the option to derived etl::message<> from a parent class other than etl::imessage.
The parent class must ultimately be derived from etl::imessage.

===============================================================================
20.11.5
Added Arduino examples.

===============================================================================
20.11.4
Fixed etl::circular_buffer copy and move assignment bug where the destination 
buffer was not cleared before assignment.

===============================================================================
20.11.3
Define missing macro when cross compiling with clang for AVR

===============================================================================
20.11.2
etl::basic_string::copy is now const and does not affect truncation flags.

===============================================================================
20.11.1
Fixed ambiguous function call in etl::mem_cast for clang.

===============================================================================
20.11.0
Added etl::mem_cast, etl::mem_cast_ptr & etl::mem_cast_types for reinterpretation of memory blocks.
State tables in etl::debounce are now constexpr in C++11 or above.

===============================================================================
20.10.6
Updated QueuedMessageRouter and QueuedFSM examples to use current message frameworks.

===============================================================================
20.10.5
Added container_type to etl::stack, etl::queue and etl::priority_queue.

===============================================================================
20.10.4
Fixed cross compiler compatibility for etl::circular_buffer.

===============================================================================
20.10.3
Fixed etl::fsm generator for non-default number of message types.

===============================================================================
20.10.2
Fixed misspelled histogram class.

===============================================================================
20.10.1
Fixed incorrect histogram end() and cend() return values.

===============================================================================
20.10.0
Added Hierarchical Finite State Machine (etl::hfsm) derived from etl::fsm

===============================================================================
20.9.3
Fixed misspelt DBL_MAX macro.

===============================================================================
20.9.2
Fixed ETL_ASSERT for non-class types in etl::pool.

===============================================================================
20.9.1
Replaced std::distance with etl::distance in erase() and erase_if() for vector.h

===============================================================================
20.9.0
Fixed #362 'etl::fsm::receive() partial override'.
Fixed #363 'circular_buffer operator [] takes integer rather than size_type'.
Fixed occasional incorrect string length for etl::make_string.
Added macros for compilers that don't support HUGE_VAL.
Added etl::accumulate, etl::clamp, etl::erase, etl::erase_if, etl::remove, etl::remove_if.
Added maths algorithms and functors.
  etl::correlation
  etl::covariance
  etl::gamma_encode
  etl:;gamma_decode
  etl::histogram
  etl::sparse_histogram
  etl::mean
  etl::invert
  etl::threshold
  etl::quantize
  etl::limiter
  etl::rescale
  etl::rms
  etl::standard_deviation
  etl::variance

===============================================================================
20.8.0
Added more CRCs, generalised table creation.
Options for table sizes of 4, 16 and 256.
Removed unnecessary non-const versions of iterators for containers.

===============================================================================
20.7.0
Added etl::selection_sort.
etl::delegate accepts moveable parameters.
Fixed the return type of const iterators for containers from const_iterator to iterator.
Changed many instances of 'static const' to 'static ETL_CONSTANT'.

===============================================================================
20.6.3
Updates to unit test CMake files.
Added missing include for string_utilities.h

===============================================================================
20.6.2
C++98/03 compatibility fixes.
Added 'sanity check' tests for checking for 98/03/11/14/17 issues.

===============================================================================
20.6.1
Added missing etl::atomic<bool> from gcc & clang implementations.
Changed nullptr to ETL_NULLPTR in buffer_descriptors and multi_range.
Fixed header includes in state_chart.h

===============================================================================
20.6.0
Added etl::message_router_registry.
Changed etl::flat_multimap & etl::flat_multiset to iterate in insertion order, as per C++11 map and set.
Added ETL_CONSTEXPR to etl::array.
C++98 compatibility fixes.
Remove unnecessary template keyword to destroy() call in etl::pool.
Abstracted unit test framework header.

===============================================================================
20.5.2
Fixed template aliases when using STL and below C++14

===============================================================================
20.5.1
Fixed ambiguous template error for etl::extent.

===============================================================================
20.5.0
Added specialisation of etl::state_chart to allow a parameter to be passed along
with the event.
Issue #339 - Fix extent type conversion warning
Issue #340 - Export headers as system includes

===============================================================================
20.4.1
Updates to etl::shared_message example application.

===============================================================================
20.4.0
Added uninitialized_resize() to etl::vector and etl::basic_string.

===============================================================================
20.3.1
Added ETL_CONSTANT to numeric_limits member functions.

===============================================================================
20.3.0
Added initialize_free_space(), trim_to_terminator() and data_end() functions to
strings for easier integration with C APIs.

=============================================================================== 
20.2.3
Fixed indexing error in find_next() for etl::bitset.

===============================================================================
20.2.2
Added non-const get_message() member functions in shared message framework.

===============================================================================
20.2.1
Modified reference_counted_message_pool::allocate() return type.
Changed from etl::ireference_counted_message* to etl::reference_counted_message<TMessage, TCounter>*

===============================================================================
20.2.0
Allow default constructed messages for shared messages.

===============================================================================
20.1.0
Changed template aliases so they are available for C++11 rather than C++14.

===============================================================================
20.0.0
Removed source 'etl::imessage_router&' parameter from the message framework 'receive'
and 'on_receive' member functions.

===============================================================================
19.5.3
Added move constructor and move assignment operator to etl::shared_message.

===============================================================================
19.5.2
Fixed rollover error for etl::queue_spsc_atomic
Added 'required_alignment' parameter to 'allocate' for etl::imemory_block_allocator.
Updated QueuedMessageRouter example.

===============================================================================
19.5.1
Exclude integral types from being considered for iterator range container constructors.

===============================================================================
19.5.0
Added shared messages to the messaging framework + supporting allocator classes.
Some refactoring of the messaging framework internals.
Added example application for shared messages.
Added a lockable queue with locks implemented as pure virtuals.
Refactored the other queues.
Fixed missing virtual destructor for C++11 observer.
Added etl::successor class for consistent 'chain of responsibilty' pattern generation.
Added missing constructors to unique_ptr.
Added nullptr check to unique_ptr destructor.
Fixed VS2019 warning for etl::deque iterators.
Added a virtual on_task_added callback to the scheduler.
Added a runtime multi range nested loop class.
Added etl::for_each.
Added is_random_access_iterator and deprecated is_random_iterator.
Added VS2019 Delegate function interrupt service example.

===============================================================================
19.4.3
Added nullptr check to unique_ptr destructor.

===============================================================================
19.4.2
Fixed VS2019 warning for etl::deque iterators.

===============================================================================
19.4.1
Added constructors with deleters for unique_ptr.

===============================================================================
19.4.0
Added virtual function 'void on_task_added()' that is called when a task is added to a scheduler.

===============================================================================
19.3.7
Fix some container iterator assignment operators to return a reference, rather than value.
Fix non-const etl::frame_check_sequence functions are const in all derived classes.
Make value getter functions const in etl::frame_check_sequence.

===============================================================================
19.3.6
Arduino compatibility mods.

===============================================================================
19.3.5
Change std::move to etl::move in etl::forward_list

===============================================================================
19.3.4
Make etl::span compliant with STL API by adding missing overloads for span::first + span::last

===============================================================================
19.3.3
Added check for existence of <new> in platform.h
Added placement_new.h which selects between <new> and ETL definitions.

===============================================================================
19.3.2
Added No-STL clang mutex that uses GCC implementation.

===============================================================================
19.3.1
Fixed etl::format_spec constexpr compatibility with C++11.
Fixed etl::bit_stream reading too many bits when reading floating point values.

===============================================================================
19.3.0
More constexpr, template aliases and inline variables.
Added ETL_ASSERT for out-of-order state list.

===============================================================================
19.2.1
Fixed version number retrieval from Github.

===============================================================================
19.2.0
Security flag for a string is copied on assignment or copy constructor.
etl::format_spec may now be a constexpr.
Added AVR check to nullptr.h

===============================================================================
19.1.0
Refactor of etl::buffer_descriptors interface.

===============================================================================
19.0.0
Containers with external buffers or pools are now separate classes instead of specialisations.

etl::circular_buffer<T, 0> => etl::circular_buffer_ext<T>
etl::forward_list<T, 0>    => etl::forward_list_ext<T>
etl::list<T, 0>            => etl::list_ext<T>
etl::string<0>             => etl::string_ext
etl::wstring<0>            => etl::wstring_ext
etl::u16string<0>          => etl::u16string_ext
etl::u32string<0>          => etl::u32string_ext
etl::vector<T, 0>          => etl::vector_ext<T>

===============================================================================
18.20.2
Fixed etl::to_string for floating point numbers between 0 & -1.0

===============================================================================
18.20.1
Resolved issue with zero length literals for etl::make_string (again!)
Remove redundant test support code.
Disabled ASAN option in Visual Studio project.

===============================================================================
18.20.0
Added etl::buffer_descriptors.
Added std/etl pair conversions.
Added etl::make_string_view.
Resolved issue with zero length literals for etl::make_string
Resolved etl::flags constexpr issues.
Added atomics for clang.
Resolved type_traits issues for GCC < v5

===============================================================================
18.19.3
Addressed ARMCC v5 C++11 issues

===============================================================================
18.19.2
Expanded the use of constexpr in etl::flags

===============================================================================
18.19.1
Added ETL_CONSTEXPR for state_chart, transition and state constructors.
Eliminate ARM compiler v5 warnings for state_chart.
Fixed return type error for atomic GCC.

===============================================================================
18.19.0
Modified strings for better memory efficiency. String truncation detection and clear-after-use can be disabled.
Added ETL_DISABLE_STRING_TRUNCATION_CHECKS macro check in platform.h.
Added ETL_DISABLE_STRING_CLEAR_AFTER_USE macro check in platform.h.
Added etl::flags to wrap boolean flag functionality.
Four parameter equal() algorithm variant added.
Modified is_pod definition when using the STL.
Added are_all_same trait.

===============================================================================
18.18.2
Change to array_view member variable declaration, for constructor from array.

===============================================================================
18.18.1
Added [] operators to etl::circular_buffer

===============================================================================
18.18.0
Added etl::circular_buffer

===============================================================================
18.17.2
Added missing emplace functions from vector-of-pointers specialisation.

===============================================================================
18.17.1
Fixed incorrect reflected CRC8 0x07 lookup table

===============================================================================
18.17.0
Added iterator API to all etl::frame_check_sequence based template classes, such as CRCs and checksums.
Example:
std::string data("123456789");
etl::crc32 crc;
std::copy(data.begin(), data.end(), crc.input());
uint32_t value = crc.value();

===============================================================================
18.16.5
Add missing include in test etl_profile.h

===============================================================================
18.16.4
Reduced warnings from cppcheck v2.2

===============================================================================
18.16.3
Added VS2019 to CI configuration file.
Created separate VS2019, GCC and clang configuration files.

===============================================================================
18.16.2
Updates to CI configuration files to compile 'No STL' variants of the tests.

===============================================================================
18.16.1
Updates to CI configuration files.

===============================================================================
18.16.0
Added template deduction guides for most containers.

===============================================================================
18.15.5
Refactored empty(), full(), available() member functions for etl::list and etl::forward_list

===============================================================================
18.15.4
Performance optimisations for etl::rotate, etl::move & etl::move_backward
when not using the STL, iterators are pointers and the objects are trivially
copyable (currently POD types).

===============================================================================
18.15.3
etl::array_view constructor from C array is no longer explicit.

===============================================================================
18.15.2
Workaround for Segger ARM Link-Time-Optimisation (LTO) bug.
etl::array_view constructor from etl or std array is no longer explicit.

===============================================================================
18.15.1
Refactoring of 18.15.0.
Modified constructor syntax.

===============================================================================
18.15.0
Allow strings with external buffers to use a pre-initialised buffer.

===============================================================================
18.14.1
Fixed conditional compilation macro use for template deduction guides.

===============================================================================
18.14.0
Added template deduction guides for array and array_view

===============================================================================
18.13.0
Added a line coordinate generator using the Bresenham algorithm.
The API is similar to a container.

===============================================================================
18.12.7
Made etl::reference_wrapper API closer to the STL version. Does not support invocation of a callable object.

===============================================================================
18.12.6
Fixed etl::stack top level assignment operator not clearing before copy.

===============================================================================
18.12.5
Fixed issue for incorrect operation of erase(const_iterator, const_iterator) when 
the terminating iterator was end() for etl::unordered_map, etl::unordered_multimap,
etl::unordered_set and etl::unordered_multiset. 

===============================================================================
18.12.4
Resolve clang 9 compatibility issues.

===============================================================================
18.12.3
Resolve 0U constant ambiguity in string utility tests

===============================================================================
18.12.2
Deleted unused file.
Updated CMakeLists.txt

===============================================================================
18.12.1
Fixed compiler compatibility issues in etl::forward_list and etl::list

===============================================================================
18.12.0
Recoded string utility get_token()
clang 9 compatibility changes

===============================================================================
18.11.1
Fix and optimise etl::list and etl::forward_list move constructors and assignment operators.

===============================================================================
18.11.0
Added etl::ibitset::span() member function to return a span of the underlying binary data.

===============================================================================
18.10.0
Fixed pointer vector move operators.
Optimised constructors and assignments for pointer vectors.

===============================================================================
18.9.0
Added enable/disable observer interface to observable class.

===============================================================================
18.8.2
Fixed incorrect return in find() and at() for non-existent key.

===============================================================================
18.8.1
Fix C++03 error_handler compatibility

===============================================================================
18.8.0
Re-coded string utilities to allow any string-like container to use it.

===============================================================================
18.7.1
Removed to_upper_case, to_lower_case & to_sentence_case from
wstring_utilities, u16string_utilities & u32string_utilities

===============================================================================
18.7.0
String utilities added.
Fixed C++03 compatibility issue in error_handler.h

===============================================================================
18.6.0
Added stream manipulators

===============================================================================
18.5.0
Added string streams
etl::string_stream
etl::wstring_stream
etl::u16string_stream
etl::u32string_stream

Added string formatting to etl::to_string from
etl::string etl::string_view
etl::wstring etl::wstring_view
etl::u16string etl::u16string_view
etl::u32string etl::u32string_view

===============================================================================
18.4.0
Refactored etl::error_handler to use etl::delegate style implementation.
Allows set_callback() function to be given run-time and compile-time pointers to free and member functions without using etl::ifunction.

===============================================================================
18.3.4
Changed std::move to etl::move in etl::optional and etl::queue
Fixed etl::span subspan with etl::dynamic_extent

===============================================================================
18.3.3
C++03 compatibility fix for type_traits.h

===============================================================================
18.3.2
C++03 compatibility fix for pool.h

===============================================================================
18.3.1
C++03 compatibility fix for type_traits.h

===============================================================================
18.3.0
Added etl::parameter_pack to easily extract information about the types in a 
template parameter pack.

===============================================================================
18.2.0
Variadic versions of etl::type_id_lookup and etl::type_type_lookup for C++11 and above.

===============================================================================
18.1.3
Added CircleCI yml file for master branch

===============================================================================
18.1.2
Fixed undefined behaviour warning for #define that contained 'define'.
Restored CMakeLists.txt to root directory.

===============================================================================
18.1.1
Fixed bug for when merging a list to itself for etl::list, etl::intrusive_list & etl::intrusive_forward_list.

===============================================================================
18.1.0
Strings may use external buffers if the 'max size' template parameter is zero.

===============================================================================
18.0.1
Fixed 'insert to empty container' bug in etl::deque.

===============================================================================
18.0.0
*************************
** API Breaking Change **
Removed template typename requirement for 'allocate' and 'create' in etl::pool
*************************

Small internal updates to state_chart
Updates to static and runtime asserts in binary.h
Added a default constructor for etl::io_port_wos
Removed deleted constructors and assignment operator for etl::null_type
Added casts to 'etl::smallest_int_for_value'
Added constexpr in place of enum for C++11 in sqrt.h
Replaced 'typedef typename etl::remove_cv<T>::type type_t' with 'typedef typename etl::remove_reference<typename etl::remove_cv<T>::type>::type type_t' in type_traits.h
Removed Windows Unicode dependency in CMakeLists.txt
Added test_log_1000_base test
Updated how conan gets the library version

===============================================================================
17.8.3
Modified etl::delegate for better lambda support.
Added etl::is_class to type_traits.h
Added missing return statement in etl::move_iterator in 'operator ='
Added support for compilers that do not support LDBL_xxx macros

===============================================================================
17.8.2
Added check for NAN, nan(), nanf() or nanl() support.

===============================================================================
17.8.1
Added determine_development_os.h to platform.h to attempt to automatically deduce the OS that the developer is using.
Added subsequent changes to unit test's etl_profile.h
Removed CMakeLists.txt that auto selected profiles header (this should be done in the project's etl_profile)
Removed profiles/etl_profile.h
Added missing tests to unit test's CMakelists.txt
Changed the wording on the website to indicate that the supplied profiles in the ETL are to be seen as examples only.

===============================================================================
17.8.0
Added is_producer() and is_consumer() to the message router interface.
Deprecated is_null_router()

===============================================================================
17.7.1
Fix etl::make_pair for C++11. Replaced etl::move with etl::forward
Added implicit conversions between etl::pair and std::pair

===============================================================================
17.7.0
Added etl::message_producer type.

===============================================================================
17.6.0
etl::array_view is non-mutable by default.
Mutable functionality is enabled by defining ETL_ARRAY_VIEW_IS_MUTABLE

===============================================================================
17.5.0
Modified etl::message_packet to allow default construction, copy/move construction
and copy/move assignment.

===============================================================================
17.4.3
Changed local 'work' variables from uint_least8_t to uint32_t to avoid possible overflow.
Fixed miss-spelt scheduler policies. Typedef'd old names for backwards compatibility.

===============================================================================
17.4.2
Make etl::span::subspan functions compatible with C++11 constexpr

===============================================================================
17.4.1
Removed double definition of default case in switch.

===============================================================================
17.4.0
Added etl::span

===============================================================================
17.3.0
Added move_iterator wrapper class.

===============================================================================
17.2.0
Added move API to unordered map and set containers.

===============================================================================
17.1.2
Created scheduler example project.

===============================================================================
17.1.1
Created CMakeLists.txt files for QueuedFSM and QueuedMessageRouter example projects.

===============================================================================
17.1.0
Removed ETL's implementation of nullptr for pre C++11 compilers and created the macro
ETL_NULLPTR for internal use. Equates to NULL or nullptr, dependent on the compiler
version and project profile.

Added partial compile time versions of binary_fill and has_zero_byte.

===============================================================================
17.0.0
Recoded binary_fill, has_zero_byte and has_byte_n as runtime functions to fix
compiler compatibility issues. All functions may be constexpr if the compiler supports it.
Added tests for binary constexpr functions.

Added option to define ETL_NO_64BIT_TYPES macro if the compiler does not support 64bit types.
Conditional compilation macros added to affected files.

Added iterator copy constructors to etl::deque.

Added code for ARM5 compiler compatibility in limits.h

Simplified conditional compilation for nullptr definition.

Changes to assign() in etl::string_view for compiler compatibility

Changes to container iterators for compiler compatibility.

===============================================================================
16.8.1
Fixed C++03 compatibility issues nullptr.h, binary.h & string_view.h
Fixed warning

===============================================================================
16.8.0
Extracted message_packet from etl::message_router for use as an independent class.

===============================================================================
16.7.1
Fix C++03 compatibility issues in memory.h and utility.h

===============================================================================
16.7.0
Updates to make unique_ptr similar to std::unique_ptr
Fixed unique_ptr swap() compilation issue
Added mutex for FreeRTOS

===============================================================================
16.6.1
etl::exchange modified for better C++03 compatibility

===============================================================================
16.6.0
rvalue reference support for heap functions and etl::priority_queue

===============================================================================
16.5.3
type_traits.h is_one_of fix for C++03

===============================================================================
16.5.2
Modified nullptr.h for better cross compiler compatibility
Removed redundant includes for etl::array

===============================================================================
16.5.1
Removed redundant include
Moved move_s definitions to avoid forward declaration

===============================================================================
16.5.0
has_value() added to etl::optional

===============================================================================
16.4.4
Added #if ETL_CPP11_SUPPORTED around etl::is_rvalue_reference

===============================================================================
16.4.3
Rearranged where etl::swap is defined to fix issues with certain compilers
Fixed most warnings for CLang

===============================================================================
16.4.2
Fix etl::pair error and warning.

===============================================================================
16.4.1
Moved icache.h to 'experimental' folder.
Removed atomic.h from 'experimental' folder.

===============================================================================
16.4.0
Added rvalue references and 'move' API to all containers, except etl::priority_queue
and etl::variant

===============================================================================
16.3.0
Added parity checksum to checksum.h.

===============================================================================
16.2.1
Updated QueuedMessageHandler example

===============================================================================
16.2.0
Added etl::heap_sort to algorithms.

===============================================================================
16.1.0
Added compile time option to make string truncation an error.
Define ETL_STRING_TRUNCATION_IS_ERROR to enable.

===============================================================================
16.0.0
Refactored the ETL's relationship with the STL
Many reverse engineered STL algorithms and traits are now available through the
ETL namespace.
When ETL_NO_STL is defined, the ETL implements its own versions of the STL code.
When ETL_NO_STL is *not* defined, the ETL act as a wrapper around the STL implementations.

===============================================================================
15.5.0
Added the ability to self determine the compiler type, version and language support
by defining ETL_AUTO_DETERMINE_COMPILER_INFO or including the 'auto.h' profile.
Added support for C++11's 'alignas' and 'alignof'
Changed 'memcpy' to 'memmove' in alternate STL algorithms.

===============================================================================
15.4.2
Fix visitor overridden test virtual visit function parameters
Reduced warnings in unit tests for CLang
Updated type_traits_generator
Added explicit construction from string_view

===============================================================================
15.4.1
Move ETL_NODISCARD definition to ETL_CPP17_SUPPORTED test

===============================================================================
15.4.0
Refactored CRC classes for better code sharing and reduced resource requirements
Added new CRC definitions

===============================================================================
15.3.1
Changes to alternate STL limits.h for ARM5 compiler compatibility

===============================================================================
15.3.0
Added etl::make_string_with_capacity

===============================================================================
15.2.1
Compile time optimisations to etl::make_string

===============================================================================
15.2.0
Added function adaptors and removed built-in sort functions from indirect_vector.
Added etl::make_string for all string types.

===============================================================================
15.1.0
Fixes to the conditional compilation of choose_tag_types.h and
choose_pair_types.h to take into account ETL_NO_STL.

===============================================================================
15.0.0
Unit tests and library code updated so that the ETL may be compiled and tested
with and without STL support.

===============================================================================
14.38.2
Added alternate 'No STL' reverse_iterator unit tests.
Fixed missing equality operator for reverse_iterator.

===============================================================================
14.38.1
Added missing C++11 specific conditional compilation in callback_timer.h

===============================================================================
14.38.0
Added optional to force string and string_view construction from character
pointers to be explicit.

===============================================================================
14.37.2
Added assert.h include to memory.h

===============================================================================
14.37.1
Fix to the return value of alternate STL 'copy'
Added delegate option to callback_timer

===============================================================================
14.37.0
Added etl::indirect_vector

===============================================================================
14.36.0
Added wchar_t, u16 and u32 version of the 'set from string' function.

===============================================================================
14.35.5
Bug fix for etl::multiset & etl::multimap erase.

===============================================================================
14.35.4
Bug fix for etl::set & etl::map lower_bound.

===============================================================================
14.35.3
Added assert when calling uninitialised delegate.

===============================================================================
14.35.2
Fixed incorrect result when rounding up to integral part.

===============================================================================
14.35.1
Fixed incorrect result for negative float to string.

===============================================================================
14.35.0
Changed namespace for alternate ETL's STL support.

===============================================================================
14.34.1
Fixed strict aliasing bug for -O3 optimisation in etl::pool

===============================================================================
14.34.0
Fix alternate STL utility.h for ARM6
Added ARM7 profiles.

===============================================================================
14.33.0
Updated unit tests to C++17

===============================================================================
14.32.0
Added Platform IO example

===============================================================================
14.31.2
More PIO json tweaks

===============================================================================
14.31.1
Fix error in PIO json

===============================================================================
14.31.0
Removed C timer library

===============================================================================
14.30.0
Allow conan's etl version metadata to automatically update via git tags

===============================================================================
14.29.4
Fixed unordered_map iterator operator* return type

===============================================================================
14.29.3
Minor updates for etl::delegate

===============================================================================
14.29.2
Fixed incorrect results returned from pointers for atomic_gcc_sync

===============================================================================
14.29.1
Added #include "stl/utility.h" to etl::optional

===============================================================================
14.29.0
Added const parameters and ETL_CONST_EXPR to etl::array_view

===============================================================================
14.28.3
Removed redundant etl::const_array_view

===============================================================================
14.28.2
Various fixes.
void assign(const_pointer, size_t) did not set the truncation flag.
Fixed resize(0) error for etl::forward_list
Removed erroneous pointers in etl::unordered_map::begin()

===============================================================================
14.28.1
Optimisation of floating point specialisations of etl::cumulative_moving_average.

===============================================================================
14.28.0
Added runtime sample size specialisations to etl::cumulative_moving_average.

===============================================================================
14.27.1
Removed ETL_IF_CONSTEXPR from etl::message_timer 'tick()'

===============================================================================
14.27.0
ETL's random number generators are now non-polymorphic by default.
Define ETL_POLYMORPHIC_RANDOM to enable previous functionality.

===============================================================================
14.26.8
Moved global operators to ETL namespace.

===============================================================================
14.26.7
Compatibility changes for GCC v5.4.

===============================================================================
14.26.6
Added variadic parameters to observer notification.

===============================================================================
14.26.5
Fixed misplaced semicolon in error_handler.h

===============================================================================
14.26.4
FSM test example fix.

===============================================================================
14.26.3
A few small optimisations to binary.h

===============================================================================
14.26.2
Added #include <new> to files using 'placement new'.

===============================================================================
14.26.1
Simplified 'to_string' templates.

===============================================================================
14.26.0
Simplified message framework internal code.
Additional receive() virtual function overload taking destination id.
Removed is_bus() member function.

===============================================================================
14.25.0
Added variadic template versions of etl::largest, etl::largest_type,
etl::largest_alignment and etl::smallest

===============================================================================
14.24.2
Fixed bug in 'vector of pointers' move constructor.

===============================================================================
14.24.1
Added compile time functor version of 'create()'.

===============================================================================
14.24.0
Added 'delegate' and 'delegate_service'.

===============================================================================
14.23.1
Added missing 'cleanup' to string's resize() method.

===============================================================================
14.23.0
Added an optional secure mode to strings so that unused space will be cleared to zero
and also cleared on destruction.

===============================================================================
14.22.1
Modified memory functions so that they will not be optimised away.

===============================================================================
14.22.0
Added etl::memory_clear and etl::memory_set utility functions.
These functions will overwrite the memory allocated to the supplied object.

===============================================================================
14.21.0
Added variadic min and max functions.
etl::multimin
etl::multimin_compare
etl::multimin_iter
etl::multimin_iter_compare
etl::multimax
etl::multimax_compare
etl::multimax_iter
etl::multimax_iter_compare
C++11 only.

===============================================================================
14.20.0
Added etl::multi_array for multi-dimensional arrays.
C++11 only.

===============================================================================
14.19.0
Added 'emplace' to etl::optional.
C++03 & C++11 variants supplied depending on compiler support.

===============================================================================
14.18.4
Fixed bug in fractional part for floating point with leading zeros after the decimal point.

===============================================================================
14.18.3
Unified 'to string' API.

===============================================================================
14.18.2
Finalised 'to string'.

===============================================================================
14.18.1
Changed etl::format_spec template to etl::basic_format_spec.
Created individual format_spec typedefs for each string type.

===============================================================================
14.18.0
Added etl::to_string, etl::to_wstring, etl::to_u16string and etl::to_u32string
plus formatting support for integrals.

===============================================================================
14.17.0
Added C++11 variadic templates for etl::observer.

===============================================================================
14.16.0
Added C++11 variadic templates for etl::visitable and etl::visitor.

===============================================================================
14.15.0
Added external buffer support for vector.

===============================================================================
14.14.2
Modified 'truncated' to only be cleared on 'clear()' or 'assign()'.
Added assignment from zero terminated string pointer.

===============================================================================
14.14.1
Fixed bug where 'truncated' was not always set correctly for strings.

===============================================================================
14.14.0
Fixed string push_back() bug where the internal terminator was not updated.
Basic Conan package added.
Added const ref istring constructors.
Updated profiles for C++17.

===============================================================================
14.13.1
Modified etl::queue_spsc_locked parameters to 'const'.

===============================================================================
14.13.0
Added etl::queue_spsc_locked with injected locking functions.

===============================================================================
14.12.0
Enabled emplace functions for 'No STL'.

===============================================================================
14.11.3
Moved C++03 force macros to test profile.

===============================================================================
14.11.2
Fix inconsistent ETL_FILE definitions.

===============================================================================
14.11.1
Fix 'force C++03' macros leftover from testing.

===============================================================================
14.11.0
Added rvalue reference interfaces to forward_list.

===============================================================================
14.10.2
Fix for unordered_multimap, unordered_set and unordered_multiset insert and erase bug.

===============================================================================
14.10.1
Fix for unordered_map insert and erase bug.

===============================================================================
14.10.0
Added ETL_NOEXCEPT macros.
Added std::forward support to alternate STL utility header.

===============================================================================
14.9.0
Added constexpr constructors to string_view and array_view.

===============================================================================
14.8.2
Added missing #include "stl/iterator.h" in frame_check_sequence.h

===============================================================================
14.8.1
Fixed bug for certain inserts in etl::vector

===============================================================================
14.8.0
Added etl::callback_service
Useful for abstracting the interrupt system from C++ handlers.

===============================================================================
14.7.2
Added #include <new> to message_router.h for improved cross platform compatibility.

===============================================================================
14.7.1
Rvalue reference C++-03/C++11 compatibility fix.

===============================================================================
14.7.0
Continuing updates for adding rvalue reference API to the containers.
etl::deque
etl::list
etl::vector

===============================================================================
14.6.1
Fixed bugs in etl::flat_map 'operator[]' and 'insert'.

===============================================================================
14.6.0
Added etl::scaled_rounding to allow selection of rounding algorithms when
emulating fixed point arithmetic with scaled integral values.

Added etl::cumulating_moving_average, implementing an algorithm for
calculating an average for a stream of samples. There are specialisations
for floating point and scaled integral sample types.

Added C++11 rvalue reference 'push' functions for etl::deque.

===============================================================================
14.5.1
Fixed deque pushes for literals.

===============================================================================
14.5.0
Added move algorithms and utility to 'alternate' STL.
Added rvalue reference API to etl::deque.

===============================================================================
14.4.0
Added C++03/C++11 emplace for deque, priority_queue, queues, stack, variant & vector.

===============================================================================
14.3.0
etl::forward_list supports shared pools.

===============================================================================
14.2.0
Added 'don't care current state' transition entry option.

===============================================================================
14.1.0
Added hash based random number generator

===============================================================================
14.0.0
The ETL is now 'all header'.

===============================================================================
13.0.0
Added bit stream serialiser/deserialiser

===============================================================================
12.1.1
Added random_pcg Permuted Congruential Generator

===============================================================================
12.0.1
Modified state_chart to accept recursive events.
Made start() virtual.

===============================================================================
12.0.0
Modified the API of etl::state_chart constructors.

===============================================================================
11.19.0
Removed push(void) push_back(void) and push_front(void) function for containers.

===============================================================================
11.18.0
Added CRC16 MODBUS

===============================================================================
11.17.1
Swapped event and current state parameters for transition constructor.

===============================================================================
11.17.0
Added etl::state_chart

===============================================================================
11.16.6
Fixed implementations of key_comp and value_comp for maps and sets

===============================================================================
11.16.5
Added 'ull' suffix to 64bit literals

===============================================================================
11.16.4
Fixed nullptr compatibility for ARM5 compiler.

===============================================================================
11.16.3
Fixed missing algorithms for No STL  option.
Improved Keil compatibility.

===============================================================================
11.15.1
io_port_test Fixed unaligned access error.
debug_count  Removed typed += & -= operators and replaced with templates.

===============================================================================
11.15.0
Added 'memory model' selection for queues to allow more efficient implementations.

Maximum queue sizes:
MEMORY_MODEL_SMALL   255 (254 for queue_spsc_atomic)
MEMORY_MODEL_MEDIUM  65535
MEMORY_MODEL_LARGE   2147483647
MEMORY_MODEL_HUGE    9223372036854775807

Fixed syntax errors highlighted by GCC v8

===============================================================================
11.14.2
Removed reference_flat_set & reference_flat_map reliance on equality.

===============================================================================
11.14.1
Removed flat_set & flat_map reliance on equality.

===============================================================================
11.14.0
Added tests for limited support for self insert for strings.
Added 'wipe_on_destruct' template class for secure wiping of objects on destruction.
Updated unique_ptr API.

===============================================================================
11.13.2
Protected destructor for some FSM classes.
Observer's remove_observer returns bool.

===============================================================================
11.13.1
Fixed vector of pointer typedefs

===============================================================================
11.13.0
Added specialisation for vector<const T*>

===============================================================================
11.12.2
Remove SFINAE from array_view.
Added default etl::less compare type appropriate map and set classes.
Moved non-template code in pvoidvector to cpp file.

===============================================================================
11.12.1
Made atomic load const for non STL versions

===============================================================================
11.12.0
Renamed STATIC_ASSERT to ETL_STATIC_ASSERT
Removed non-conforming std::nullptr

===============================================================================
11.11.1
Compatibility changes for Segger IDE, GCC & STLPort

===============================================================================
11.11.0
Compatibility changes for Segger IDE, GCC & STLPort

===============================================================================
11.10.0
Merged CMake branch

===============================================================================
11.9.2
Fixed compile error when ETL_DEBUG_COUNT is not defined.

===============================================================================
11.9.1
Fix Github issue #73 (Timers)

===============================================================================
11.9.0
Added CRC32-C (Castagnoli)

===============================================================================
11.8.0
Added more binary utilities.
binary_fill
has_zero_byte
has_byte_n

===============================================================================
11.7.0
Modified header guards.
Added etl::type_select
Added etl::null_type

===============================================================================
11.6.0
Added capacity() to etl::queue
Prefixed max_size() and capacity() with ETL_CONSTEXPR in all queue types.

===============================================================================
11.5.0
Added etl::permutations and etl::combinations constant templates.

===============================================================================
11.4.0
Added improved atomics.
Added mutex
Added SPSC & MPPC queues

===============================================================================
11.3.0
Improved compatibility with 64 bit platforms.

===============================================================================
11.2.0
Added std::initializer_list constructors to containers, if ETL_CPP11_SUPPORTED is set to 1

===============================================================================
11.0.1
Added reset() to etl::optional

===============================================================================
11.0.0
New directory structure.
C & CPP files in src/
H files in include/etl/

===============================================================================
10.21.2
Added version.h

===============================================================================
10.21.1
Removal of GCC warnings from variant.h.

===============================================================================
10.21.0
Completion of operator set for etl::optional
Removal of more GCC warnings when using -Wextra.

===============================================================================
10.20.0
Rewrite of debounce code to factor out commonality.
Made interrupt locks in C timer framework to match that of C++ version.
Improved etl::endianness. Added static functions.

===============================================================================
10.19.2
Fixed strict aliasing warnings for endianness.

===============================================================================
10.19.1
Fixed strict aliasing warnings for aligned storage.

===============================================================================
10.19.0
Added 'create' and 'destroy' functions to pools.
Modified class hierarchy.
etl::generic_pool is derived from on etl::ipool.
etl::pool is derived from etl::generic_pool.

===============================================================================
10.18.1
Reduced disable/enable time during function calls.

===============================================================================
10.18.0
Improvements to message and callback timer frameworks.
Reduced disable/enable time during function calls.
Added the option to use either atomic semaphores or interrupt enables to control access.

===============================================================================
10.17.0
Added emplace functions to etl::variant.

===============================================================================
10.16.1
Improved performance of emplace for value_type parameters.

===============================================================================
10.16.0
Added emplace member functions to flat_map, flat_multimap, flat_set and flat_multiset

===============================================================================
10.15.0
Added protected destructors to FSM & message_timer and code to message router packet destructor to choose correct method of destruction.

===============================================================================
10.14.0
Added variant_pool generator.

===============================================================================
10.13.0
There was no version 10.13.0

===============================================================================
10.12.0
Re-written to avoid 'undefined behavior' by allowing containers to be polymorphic or not base on a compile time macro.

===============================================================================
10.11.2
GCC compatibility changes.
===============================================================================
10.11.1
GCC compatibility changes.
===============================================================================
10.11.0
Added ETL_CONSTEXPR macro and applied to various functions.
Allows C++11 and above compilers to set functions as constexpr.

===============================================================================
10.10.0
Added array_wrapper

===============================================================================
10.9.0

Array view
  Added array_view.

===============================================================================
10.8.1

Pool
  Changed alignof to etl::alignment_of

===============================================================================
10.8.0

Added etl::variant_pool as a replacement for etl::factory.
Deprecated etl::factory

etl::forward_list
  Renamed include guard to avoid clash with list.

Removed factory from unit tests.

multimap & multiset
  Changed static const to enum.

hash & strings
  Removed default function template parameter value.

FSM
  Moved get_fsm_context() from public to protected in etl::state

Binary
  Added sign_extend functions with shift parameter.
  Added new binary.cpp for non-template functions.
  Added bit<> template constant
  Added bit enumerations

Debug count
  Added clear()

Type lookup
  Simplified codebase

Message router
  Added 'successor' member to allow implementation 'Chain Of Responsibility' pattern.

IO Ports
  Changes value() to read().
  Rewrite of classes to improve efficiency by removing iterator indirection step.
  Fixed inconsistencies in the dynamic IO port API.

Type traits
  Added 'conditional_integral_constant' to complement 'conditional'
~~~~