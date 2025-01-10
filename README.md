# Go Race Condition Example

This repository demonstrates a simple race condition in Go using channels.  The program launches multiple goroutines that attempt to receive values from a single channel without proper synchronization.  This can lead to unexpected results and data inconsistencies.

## Problem

The `bug.go` file contains a program where multiple goroutines compete to receive values from a channel (`ch`).  Because there's no synchronization mechanism to control the order of access, this results in a race condition.

## Solution

The `bugSolution.go` file provides a corrected version using a buffered channel to avoid the race condition.  A buffered channel allows multiple goroutines to send values concurrently without blocking until they are all received. This ensures predictable behavior and prevents data corruption.