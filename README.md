# baseball-lessons
baseball lesson code
import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { Baseball, CalendarDays, Info } from "lucide-react";

const lessons = [
  {
    title: "Hitting Basics",
    description: "Learn how to stand, swing, and make contact with the ball.",
  },
  {
    title: "Throwing Technique",
    description: "Proper grip, stance, and motion for accurate throws.",
  },
  {
    title: "Catching Fundamentals",
    description: "Master catching pop-ups, grounders, and line drives.",
  },
  {
    title: "Running the Bases",
    description: "Understand base running rules and how to sprint effectively.",
  },
];

export default function KidsBaseballLessons() {
  return (
    <main className="min-h-screen bg-blue-50 p-8 space-y-16">
      <section>
        <motion.h1
          className="text-4xl font-bold text-center mb-10 text-blue-800"
          initial={{ opacity: 0, y: -20 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.5 }}
        >
          <Baseball className="inline-block mr-2" />
          Kids Baseball Lessons
        </motion.h1>
        <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
          {lessons.map((lesson, index) => (
            <motion.div
              key={index}
              whileHover={{ scale: 1.05 }}
              whileTap={{ scale: 0.95 }}
            >
              <Card className="rounded-2xl shadow-md bg-white">
                <CardContent className="p-6">
                  <h2 className="text-xl font-semibold text-blue-700">
                    {lesson.title}
                  </h2>
                  <p className="text-gray-600 mt-2">{lesson.description}</p>
                  <Button className="mt-4" variant="outline">
                    Learn More
                  </Button>
                </CardContent>
              </Card>
            </motion.div>
          ))}
        </div>
      </section>

      <section className="bg-white p-6 rounded-2xl shadow-md">
        <h2 className="text-2xl font-bold text-blue-800 flex items-center mb-4">
          <CalendarDays className="mr-2" /> Book a Lesson
        </h2>
        <p className="text-gray-700 mb-4">
          Schedule a personalized lesson with one of our friendly and experienced coaches. Just pick a time that works best for you!
        </p>
        <Button className="bg-blue-600 text-white hover:bg-blue-700">
          Schedule Now
        </Button>
      </section>

      <section className="bg-white p-6 rounded-2xl shadow-md">
        <h2 className="text-2xl font-bold text-blue-800 flex items-center mb-4">
          <Info className="mr-2" /> About Us
        </h2>
        <p className="text-gray-700">
          We're a team of passionate baseball coaches dedicated to helping kids learn and love the game of baseball. With a focus on fun, safety, and skill-building, our lessons are designed for all experience levels.
        </p>
      </section>
    </main>
  );
}
