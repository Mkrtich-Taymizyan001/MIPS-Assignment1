# 42-conversions-Mkrtich-Taymizyan001
42-conversions-Mkrtich-Taymizyan001 created by GitHub Classroom
# Task: Write a MIPS subroutine to convert a 32-bit unsigned number into a sequence of ASCII characters.  Each of these ASCII characters are printed to stdout in turn.
# The ASCII string created on stdout will be the corresponding (unsigned) decimal number, written in reverse.
# The subroutine returns the number of characters printed.
---
# Name: percent_base_10
# File: conversion.s
# Declaration:  int percent_base_10( int value)
# Semantics:
#    - iteratively divides the input value by 10.
#    - converts the remainder to ASCII
#    - print outs the ASCII character to the stdout
#    - returns the number of ASCII characters printed
# Edge Condition:
#    - value = 0;
# Question: 
#    - Should you use a while, for, or do-while loop?
#
# Starter Code:
    .text
    .globl main
main: 
    # $t1: count
    li $a0, 1234        # count = percent_base_10(1234)
    jal percent_base_10
    move $t1, $v0       
    li $a0, '\n'        # print_char('\n')
    li $v0, 11
    syscall
    move $a0, $t1       # print_int(count)
    li $v0, 1
    syscall
    li $a0, 0       # exit(0)
    li $v0, 17
    syscall
percent_base_10:
    # $v0: count
    # $a0: value
    #
    jr $ra
# Sample Output
4321
4
